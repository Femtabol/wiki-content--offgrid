# Network_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Network_Lua_API*

*Scraped on: 2025-05-02 18:42:00*

# Network
## Description
Network API handles netwroks, connecting and disconnecting devices, and sending data between characters and devices.
## Functions
### CreateDataPoint
```
Network.CreateDataPoint(internalName, dataTable, locationObject, characterName, networkName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
| dataTable | Lua Table |
| locationObject | string |
| characterName | string |
| networkName | string |


**Description**: Create a DataPoint in a specific place, from a specific character, with pre filled in data.
**Returns**: Nothing
### ConnectToNetwork
```
Network.ConnectToNetwork(connector, targetNetwork, accessKey)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| connector | Lua Type |
| targetNetwork | string |
| accessKey | string |

**Description**: Connect a device (or a table of devices) to a specified network
**Returns**: Nothing
### SendData
```
Network.SendData(internalName, dataTable, sender, receiver)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
| dataTable | Lua Table |
| sender | Lua Type |
| receiver | Lua Type |

**Description**: Send a data file from one device to another
**Returns**: Nothing
**Notes**: Much like _ConnectToNetwork_ both _senderName_ and _receiverName_ can be character names (assuming those characters have net devices)
### SetNetDeviceNFCData
```
Network.SetNetDeviceNFCData(internalName, dataTable, deviceTable)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
| dataTable | Lua Table |
| deviceTable | Lua Table |

**Description**: Sets NFC data on a mission object
**Returns**: Nothing
### SetNetDeviceNFC
```
Network.SetNetDeviceNFC(deviceName, enabled)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| enabled | bool |

**Description**: Set if a mission object supports NFCAddNetDevice
**Returns**: Nothing
