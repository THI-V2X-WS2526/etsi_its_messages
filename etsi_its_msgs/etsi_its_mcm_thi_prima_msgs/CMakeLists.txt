cmake_minimum_required(VERSION 3.5)
project(etsi_its_mcm_thi_prima_msgs)

find_package(ros_environment REQUIRED QUIET)
set(ROS_VERSION $ENV{ROS_VERSION})

# === ROS 2 (AMENT) ============================================================
if(${ROS_VERSION} EQUAL 2)

  find_package(ament_cmake REQUIRED)
  find_package(rosidl_default_generators REQUIRED)

  set(msg_files
    "msg/AccelerationConfidence.msg"
    "msg/AccelerationControl.msg"
    "msg/AccidentSubCauseCode.msg"
    "msg/ActionID.msg"
    "msg/AdverseWeatherConditionAdhesionSubCauseCode.msg"
    "msg/AdverseWeatherConditionExtremeWeatherConditionSubCauseCode.msg"
    "msg/AdverseWeatherConditionPrecipitationSubCauseCode.msg"
    "msg/AdverseWeatherConditionVisibilitySubCauseCode.msg"
    "msg/Altitude.msg"
    "msg/AltitudeConfidence.msg"
    "msg/AltitudeValue.msg"
    "msg/BasicContainer.msg"
    "msg/BasicContainerMCM.msg"
    "msg/BasicVehicleContainerHighFrequency.msg"
    "msg/BasicVehicleContainerLowFrequency.msg"
    "msg/CAM.msg"
    "msg/CamParameters.msg"
    "msg/CauseCode.msg"
    "msg/CauseCodeType.msg"
    "msg/CenDsrcTollingZone.msg"
    "msg/CenDsrcTollingZoneID.msg"
    "msg/ClosedLanes.msg"
    "msg/CollisionRiskSubCauseCode.msg"
    "msg/CoopAwareness.msg"
    "msg/CooperationCostTrajectory.msg"
    "msg/CooperationID.msg"
    "msg/CooperationTypeMCM.msg"
    "msg/Curvature.msg"
    "msg/CurvatureCalculationMode.msg"
    "msg/CurvatureConfidence.msg"
    "msg/CurvatureValue.msg"
    "msg/DangerousEndOfQueueSubCauseCode.msg"
    "msg/DangerousGoodsBasic.msg"
    "msg/DangerousGoodsContainer.msg"
    "msg/DangerousGoodsExtended.msg"
    "msg/DangerousSituationSubCauseCode.msg"
    "msg/DeltaAltitude.msg"
    "msg/DeltaLatitude.msg"
    "msg/DeltaLongitude.msg"
    "msg/DeltaReferencePosition.msg"
    "msg/DigitalMap.msg"
    "msg/DriveDirection.msg"
    "msg/DrivingLaneStatus.msg"
    "msg/EmbarkationStatus.msg"
    "msg/EmergencyContainer.msg"
    "msg/EmergencyPriority.msg"
    "msg/EmergencyVehicleApproachingSubCauseCode.msg"
    "msg/EnergyStorageType.msg"
    "msg/EventHistory.msg"
    "msg/EventPoint.msg"
    "msg/ExteriorLights.msg"
    "msg/GenerationDeltaTime.msg"
    "msg/HardShoulderStatus.msg"
    "msg/HazardousLocationAnimalOnTheRoadSubCauseCode.msg"
    "msg/HazardousLocationDangerousCurveSubCauseCode.msg"
    "msg/HazardousLocationObstacleOnTheRoadSubCauseCode.msg"
    "msg/HazardousLocationSurfaceConditionSubCauseCode.msg"
    "msg/Heading.msg"
    "msg/HeadingConfidence.msg"
    "msg/HeadingValue.msg"
    "msg/HeightLonCarr.msg"
    "msg/HighFrequencyContainer.msg"
    "msg/HumanPresenceOnTheRoadSubCauseCode.msg"
    "msg/HumanProblemSubCauseCode.msg"
    "msg/InformationQuality.msg"
    "msg/IntentionSharingContainer.msg"
    "msg/ItineraryPath.msg"
    "msg/ItsPduHeader.msg"
    "msg/LanePosition.msg"
    "msg/LateralAcceleration.msg"
    "msg/LateralAccelerationValue.msg"
    "msg/Latitude.msg"
    "msg/LightBarSirenInUse.msg"
    "msg/Longitude.msg"
    "msg/LongitudinalAcceleration.msg"
    "msg/LongitudinalAccelerationValue.msg"
    "msg/LowFrequencyContainer.msg"
    "msg/MCM.msg"
    "msg/ManeuverCoordinationContainer.msg"
    "msg/ManeuverCoordinationMessage.msg"
    "msg/ManeuverExecutionContainer.msg"
    "msg/ManeuverNegotiationContainer.msg"
    "msg/McmCategory.msg"
    "msg/McmParameters.msg"
    "msg/NumberOfOccupants.msg"
    "msg/NumberOfVehicles.msg"
    "msg/OpeningDaysHours.msg"
    "msg/PathDeltaTime.msg"
    "msg/PathHistory.msg"
    "msg/PathPoint.msg"
    "msg/PerformanceClass.msg"
    "msg/PhoneNumber.msg"
    "msg/PosCentMass.msg"
    "msg/PosConfidenceEllipse.msg"
    "msg/PosFrontAx.msg"
    "msg/PosLonCarr.msg"
    "msg/PosPillar.msg"
    "msg/PositionOfOccupants.msg"
    "msg/PositionOfPillars.msg"
    "msg/PositioningSolutionType.msg"
    "msg/PostCrashSubCauseCode.msg"
    "msg/PriorityManeuver.msg"
    "msg/ProtectedCommunicationZone.msg"
    "msg/ProtectedCommunicationZonesRSU.msg"
    "msg/ProtectedZoneID.msg"
    "msg/ProtectedZoneRadius.msg"
    "msg/ProtectedZoneType.msg"
    "msg/PtActivation.msg"
    "msg/PtActivationData.msg"
    "msg/PtActivationType.msg"
    "msg/PublicTransportContainer.msg"
    "msg/RSUContainerHighFrequency.msg"
    "msg/Reason.msg"
    "msg/ReasonReject.msg"
    "msg/ReferencePosition.msg"
    "msg/RelevanceDistance.msg"
    "msg/RelevanceTrafficDirection.msg"
    "msg/RequestID.msg"
    "msg/RequestResponseIndication.msg"
    "msg/RescueAndRecoveryWorkInProgressSubCauseCode.msg"
    "msg/RescueContainer.msg"
    "msg/RestrictedTypes.msg"
    "msg/RoadType.msg"
    "msg/RoadWorksContainerBasic.msg"
    "msg/RoadworksSubCauseCode.msg"
    "msg/SafetyCarContainer.msg"
    "msg/SemiAxisLength.msg"
    "msg/SequenceNumber.msg"
    "msg/SignalViolationSubCauseCode.msg"
    "msg/SlowVehicleSubCauseCode.msg"
    "msg/SpecialTransportContainer.msg"
    "msg/SpecialTransportType.msg"
    "msg/SpecialVehicleContainer.msg"
    "msg/Speed.msg"
    "msg/SpeedConfidence.msg"
    "msg/SpeedLimit.msg"
    "msg/SpeedValue.msg"
    "msg/StationID.msg"
    "msg/StationType.msg"
    "msg/StationarySince.msg"
    "msg/StationaryVehicleSubCauseCode.msg"
    "msg/SteeringWheelAngle.msg"
    "msg/SteeringWheelAngleConfidence.msg"
    "msg/SteeringWheelAngleValue.msg"
    "msg/SubCauseCodeType.msg"
    "msg/Temperature.msg"
    "msg/TimestampIts.msg"
    "msg/Traces.msg"
    "msg/TrafficConditionSubCauseCode.msg"
    "msg/TrafficRule.msg"
    "msg/TrajectoryMCM.msg"
    "msg/TrajectoryOffsetPoint.msg"
    "msg/TrajectoryOffsetTime.msg"
    "msg/TrajectoryPointMCM.msg"
    "msg/TransmissionInterval.msg"
    "msg/TurningRadius.msg"
    "msg/VDS.msg"
    "msg/ValidityDuration.msg"
    "msg/VehicleAutomationLevel.msg"
    "msg/VehicleBreakdownSubCauseCode.msg"
    "msg/VehicleIdentification.msg"
    "msg/VehicleLength.msg"
    "msg/VehicleLengthConfidenceIndication.msg"
    "msg/VehicleLengthValue.msg"
    "msg/VehicleMass.msg"
    "msg/VehicleRole.msg"
    "msg/VehicleWidth.msg"
    "msg/VerticalAcceleration.msg"
    "msg/VerticalAccelerationValue.msg"
    "msg/WMInumber.msg"
    "msg/WheelBaseVehicle.msg"
    "msg/WrongWayDrivingSubCauseCode.msg"
    "msg/YawRate.msg"
    "msg/YawRateConfidence.msg"
    "msg/YawRateValue.msg"
  )

  rosidl_generate_interfaces(${PROJECT_NAME}
    ${msg_files}
  )

  ament_export_dependencies(rosidl_default_runtime)

  ament_package()

# === ROS (CATKIN) =============================================================
elseif(${ROS_VERSION} EQUAL 1)

  find_package(catkin REQUIRED COMPONENTS
    message_generation
    std_msgs
  )

  add_message_files(DIRECTORY msg)

  generate_messages(
    DEPENDENCIES std_msgs
  )

  catkin_package(
    CATKIN_DEPENDS
      message_runtime
      std_msgs
  )

endif()
