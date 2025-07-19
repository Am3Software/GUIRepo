%% ---------- README JWRAPPER - OPENVSP2MATLAB ---------- %%

 This README is related to the importAC.exe - This version of the executable is valid for a certain number of days from the release date. ( See at start of the importAC.exe )
 To unlock a perpetual version please contact : amedeo.falco@unina.it
 
 1) The .exe has been compiled with the R2025a MATLAB version. If you don't have this release
 please, go to the following link https://it.mathworks.com/products/compiler/matlab-runtime.html 
 and install the MATLAB Runtime 25.1 on your Pc
 
 2) To download some packages necessary to the importAC.exe, please, download and install
 GitBush at following link https://git-scm.com/downloads
 Ensure system compatibility and proceed with the guided installation. Use all default settings unless otherwise specified.
 
 3) After the installation a folder called Hangar will be downloaded. In this folder there are some aircrafts that you can customize
 directly from the OpenVSP GUI, clicking the "Edit AC" button of the importAC_GUI. When you've done, save your AC in the Hangar folder.
 
 4) You can also select an aircraft already available in the Hangar using the dropdown menu next to the "nameOfAircraft" field in the GUI.
 
 5) Launch the GUI clicking on "importAC_GUI.exe". Edit all the desired fields and then click on 
 
    * Save XML
	
 6) If you desire to create a new aircraft or to modify an exsiting aircrfat click on 
    
	* Edit AC 

	If you select an AC from the dropdown menu, clicking on the "Edit AC" button you'll enable to edit the related .vsp3, otherwise a blank scketch pad will be opned.
	When you have completed your edit, please save the AC in the folder Hangar, than click on "Refresh GUI" button to enable the modifications.
	
 7) The code automatically recognize the "typeOfTail" fiel of an aircraft stored in the Hangar. When you select one of them, please rember always to click on the
    "Save XML" button to enable final modification related to the XML, useful to start the analysis.
 
 8) The tool check for an upgrade of the file exe called 'importAC'. If an update is detected please following instructions
 
   * Read all the info displayed and then close the current importAC.exe window  
   * From the GUI, click on the "Update importAC" button
   * Then click again on the "Run code" button to launch the analysis with the new version of importAC.
   
   Please, periodically check also for a GUI update, clicking on the "Update GUI" button. If there will be an update, please, follow the displayed istructions.

 
 9) If you want to add a nacelle to a turboprop aircraft, consider adding a POD geometry in OpenVSP and renaming it as propeller_# (where # = 1, 2, 3, ... n).
 If you want to add a turbofan, consider adding a Stack geometry from the Geometry Browser in OpenVSP and renaming it as nacelle_# (where # = 1, 2, 3, ... n).
 
 10) It's higly suggested to customize a model already stored in the Hangar folder. When you have modified the AC, please save the AC as follows:
 
    * original_name_of_the_aircraft_Modified.vsp3
 
 11) Concerning the lifting surfaces you must renaming it as:
 
    * wing
	* horizontal
	* vertical
	* canardWing or canard
	
   Instead, concerning to the fuselage, renaming it as 'fuselage'.
   
 12) Related to the control surfaces on a lift surface you must rename them as follows
 
     * slat_# (where # = 1,2,3,...,n)
     * flap_# (where # = 1,2,3,...,n)
	 * flapCanard
	 * aileron
	 * elevator
	 * rudder_# (where # = 1,2,3,...,n)
	 
 13) In the tab 'Control Grouping' ,related to VSPAERO, you must create the following control groupings:
 
     * SLAT
	 * FLAP
	 * CANARD
	 * ELEVATOR
	 * RUDDER
	 
   Then, add to each 'Control Grouping' the related control surface both for _Surf0 and _Surf1
   
   
 14) The following configurations are available. Enter one or more (comma‑separated) configurations in the ‘configToAnalyze’ field of the GUI:
 
  <!-- Type of Configuration(s)** -->
  <!-- %      baseline = automatically detected
  %           W       = wing
  %           H       = horizontal
  %           C       = canard
  %           BH      = body horizontal
  %           BC      = body canard
  %           WP      = wing propeller
  %           WB      = wing body
  %           WH      = wing horizontal
  %           WV      = wing vertical
  %           WHP      = wing horizontal propeller
  %           WHF      = wing horizontal fan
  %           WVP      = wing vertical propeller
  %           WVF      = wing vertical fan
  %           WBH      = wing body horizontal
  %           WBC      = wing body canard
  %           WBHP     = wing body horizontal propeller
  %           WBHF     = wing body horizontal fan
  %           WBVP     = wing body vertical propeller
  %           WBVF     = wing body vertical fan
  %           WBV     = wing body vertical
  %           WBHV    = wing body horizontal vertical
  %           WBHVC   = wing body horizontal vertical canard
  %           WBHVP   = wing body horizontal vertical propeller
  %           WBHVF   = wing body horizontal vertical fan
  %           WBHVCBO = wing body horizontal vertical canard boom
  %           WBHVCBOP = wing body horizontal vertical canard boom propeller
  %           WBHBO   = wing body horizontal boom
  %           WBVBO   = wing body vertical boom
  %           WBHBOP  = wing body horizontal boom propeller
  %           WBVBOP  = wing body vertical boom propeller
  %           WBHVBO  = wing body horizontal vertical boom
  %           WBHVBOP  = wing body horizontal vertical boom propeller-->
   
 15) If you have an UAV the EO/IR sensor turret must be renamed as 'eoir'.
 
 16) When you have a Vee-Tail consider to analyze the configuration WBH to enable the elevator and the configuration WBV to enable the rudder.
 
 17) If you want to enable 'Visual Post-Processing' related to the 'Launch Viewer' of VSPAERO, you must set 'isRequestedVisualPostProcessing' to true.
 Then, for each configuration you have analyzed, you can decide to apply the 'Launch Viewer' through a boolean value (true or false) in the field 'isRequestedLaunchViewer'.
 When the 'Launch Viewer' dialog window opens, you can set everything you need.
 However, remember that to switch to the next case, you must first close the current dialog window.

 18) Related to aeroSettingsTest.xml and to Function_Import_AC_Test. 

 Related to aileron, elevator and rudder is possible to set a multiple deflection.
	    * activeMD                   = true or false to enable or desable the multiple deflection
		* configToMultipleDeflection = set your desried config or multiple config where apply the multiple deflection
		* priority                   = set the priority of a configuration with respect to the others, where 1 = Max - 2 = Midimum  - 3 = Low.
		
 When a multiple delfection is activate with a multiple config, in the field 'isRequestedLaunchViewer', please set to true/false as many times as there are activated configurations. 


 19) When you want to activate more than one control surface in the same analysis, consider to insert in the field 'configToAnalyze', the related config
    as many times as there are activatedMD.
 