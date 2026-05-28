# Fivem-farm-system-
Fivem Farm system essentialmode 

# 🌾 Farm Script - Advanced Farming System
### FiveM | EssentialMode | mysql-async

---

## 📋 Features

- **6 land types** with 10, 15, 20, 30, 40, and 50 planting slots
- **Land prices**: $1M, $5M, $10M, $30M, $40M, $50M
- **Private password system** for each land + password change support
- **6 plant types**: Wheat, Corn, Grapes, Potato, Tomato, Industrial Cannabis
- **Watering system**: Every plant requires watering (Hold E for 5 seconds)
- **Real-time growth**: Each plant has its own growth duration
- **Floating growth percentage display** above plants with colored progress
- **Harvest system** with E (5 seconds) when growth reaches 100%
- **Uproot system** with G (5 seconds) without receiving items
- **Farm storage** for harvested products
- **Automatic deletion** of unharvested plants after 30 hours
- **Exit tractor** available near the farm entrance
- **Restriction**: Each player can own only 1 land per farm

---

## ⚙️ Installation

### 1. Database

Run the `farm_script.sql` file in your database:

```sql
source /path/to/farm_script.sql
Or tables will be automatically created when the resource starts.
2. Files
Place the farm_script folder inside your server resources directory:
resources/
  └── farm_script/
      ├── fxmanifest.lua
      ├── config.lua
      ├── farm_script.sql
      ├── client/
      ├── server/
      └── html/
3. server.cfg
ensure mysql-async
ensure essentialmode
ensure farm_script
📦 Dependencies
Resource
Version
mysql-async
Latest
essentialmode
Latest
🗺 Farm Coordinates
You can change farm coordinates inside config.lua:
Config.Farms[1] = {
    enterCoords = vector3(X, Y, Z),       -- Entrance point
    tractorCoords = vector4(X, Y, Z, H), -- Exit tractor
    landCoords = { ... },                -- Planting slots
}
🌱 Plants
Plant
Seed
Harvest
Grow Time
Wheat
wheat_seed
wheat
15 Minutes
Corn
corn_seed
corn
40 Minutes
Grapes
grape_seed
grape
20 Minutes
Potato
potato_seed
potato
25 Minutes
Tomato
tomato_seed
tomato
30 Minutes
Industrial Cannabis
cannabis_seed
cannabis
60 Minutes
To add a new plant in config.lua:
Config.Plants["myplant"] = {
    label = "Plant Name",
    seed_item = "myplant_seed",
    harvest_item = "myplant",
    harvest_amount = {min = 3, max = 6},
    grow_time = 20 * 60,        -- 20 minutes
    expire_time = 30 * 60 * 60, -- 30 hours
    prop = "prop_plant_fern_01",
    prop_grown = "prop_bush_lush_01",
    water_needed = true,
}
💰 Land Pricing
Farm Type
Slots
Price
Small Farm
10
$1,000,000
Medium Small Farm
15
$5,000,000
Medium Farm
20
$10,000,000
Large Farm
30
$30,000,000
Bigger Farm
40
$40,000,000
Massive Farm
50
$50,000,000
🎮 Controls
Key
Action
E near entrance
Open farm menu
E near thirsty plant
Water plant (5 sec)
E near ready plant
Harvest plant (5 sec)
G near any plant
Uproot plant (5 sec)
Enter tractor
Exit farm
🔧 Editable Configs in config.lua
Config.WateringTime = 5000   -- Watering duration (ms)
Config.HarvestTime  = 5000   -- Harvest duration (ms)
Config.UprootTime   = 5000   -- Uproot duration (ms)
Config.LandKey      = 1000   -- Total land keys
Config.TractorModel = "TractorFR" -- Tractor model
📝 Important Notes
Item System
To check player seeds/items, complete the related code inside server/plants.lua (PlantSeed) according to your inventory system.
Money System
EssentialMode money check/remove functions are already included in server/main.lua. Adjust them if needed for your framework.
Coordinates
All default coordinates are placeholders. Use /coords or teleport and set your real farm locations manually.
❤️ Credits
Developed for FiveM roleplay servers with ❤️
