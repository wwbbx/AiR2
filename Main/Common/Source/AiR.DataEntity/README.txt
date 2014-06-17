Later on this README maybe revised according to correct document instruction that it should provided.

2014.06.17
According to my current thought, AiR Lite is the one that will loading Calibration Results
then print report directly.

Although CalibrationResults are not final result data, it has default expected measured value
and those value are enough for us to generate report to verify my thought on AiR Lite = EMU.

Next step, I will implement very straight forward script procedure that will control only one
suite of ETE to generate measurement result data. Then print the report. I call it AiR Mono = Semi-Auto EMU.

In the future, I want to make AiR to have complex script support like STE. So AiR = STE.

-----------------------------------------------------------------------------------------------

Here is my development sequence that I think I can insistent on:

	10. DataEntity/CalibrationResult -> ReportGenerator
	20. Application Structure. It should be the compiled from future application scripts.
	30. Platform Architecture/Components/Modules that support application.
	40. Application Compiler that will compile application script to final application.
		Currently I am using C#, but later on, we can any other language. I can take
		Java as example to verify my thought.
	50. Test Cases for AiR Lite, AiR Mono and AiR. Those are my fixture to develop every "Next Generation"
		calibration platform. It is the secrat part that I should keep it as confidencial.
	60. IDE that can help application developer to create application script easily.
		Application Developers are theorily metrologist. They don't know C# programming. But they are
		measurement experts.

-------------------------------------------------------------------------------------------------

ICalibrationResult is the root entry for CalibrationResults.

ICalibrationResult contains:
	10. IDeviceUnderTestInfo
	20. ICalibrationServiceInfo
	30. IMeasurementResult+

IMeasurementResult contains:
	10. Name
	20. IMeasurementDataSection+

IMeasurementDataSection contains:
	10. Name
	20. IMeasurementPoint+

IMeasurementPoint contains:
	10. GUID
	20. IMeasurementValue+

IMeasurementValue contains:
	10. Role
	20. Name
	30. Value
	40. Unit

----------------------------------------------------------------------------------------------------

I will use JSON to serialize/deserialize ICalibrationResult object.

================================================================================================
ENOUGH for the document now. No one will read longer README. Writing more is pointless.