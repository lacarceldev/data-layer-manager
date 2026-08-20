# RUNTIME DATA LAYER MANAGER v1.0



This plugin is designed to dynamically load and unload Data Layers at runtime. It is ideal for executing seamless environment transitions out of the player's line of sight—a technique commonly used in horror titles and games featuring dynamic level mechanics. Additionally, the plugin includes a Data Layer state saving system and an organizational framework to group Data Layers under primary categories, making it fully scalable across all game levels.



This plugin was developed and tested in version 5.8 (including subsequent hotfixes). Full compatibility with other engine versions cannot be guaranteed.



###### **Plugin Contents**



* **E\_MainLayers:** Enumerator to define your primary world zones (e.g., Forest, Beach, City).
* **F\_DataLayers**: Structure containing separate arrays for loaded and unloaded Data Layers.
* **BI\_DataLayer:** Blueprint Interface providing optimized functions for Data Layer management.
* **GI\_DataLayerManagement**: GameInstance containing the core framework, ensuring runtime accessibility across all levels. Set this as your default GameInstance in Project Settings or integrate its logic into your existing custom GameInstance.
* **SG\_DataLayers:** SaveGame object responsible for persisting and restoring Data Layer states.



###### **Installation**



1. Download and extract the archive.
2. Copy the RuntimeDataLayerManager folder into your project's Plugins directory (create the Plugins folder at the project root if it does not exist).
3. Open your project, navigate to Edit -> Plugins, locate RuntimeDataLayerManager, ensure it is enabled, and restart the editor.



###### **Setup \& Prerequisites**



1. Follow these steps to configure the system:
2. Ensure World Partition is enabled in your level to utilize Data Layers.
3. In the Content Browser settings, enable Show Plugin Content, then navigate to /RuntimeDataLayerManager.
4. Open E\_MainLayers and populate it with your primary zones/levels.
5. In GI\_DataLayerManagement, populate the DataLayerCatalog map by assigning Data Layers and their default states (Loaded or Unloaded) to the corresponding E\_MainLayers entries. Note: The initial state defined here must match the default state of the Data Layers placed in your scene.
6. In Project Settings, assign GI\_DataLayerManagement as your default Game Instance (or migrate its logic into your custom GameInstance).



###### **Usage Guide**



Execute the following interface functions wherever environment changes are required:



* Unload a Data Layer: Call **DataLayerToUnload**, specifying the target Main Layer and the Data Layer to unload.
* Load a Data Layer: Call **DataLayerToLoad**, specifying the target Main Layer and the Data Layer to load.
* State Persistence: When reaching a checkpoint or saving game progress, call **SaveDataLayerState** alongside your primary save routine to store the current layer states. Alternatively, you can access the variable data directly to handle custom save logic.



I hope this plugin helps streamline your project's development workflow!

