---
title: IMetaDataEmit-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit
helpviewer_keywords:
- IMetaDataEmit interface [.NET Framework metadata]
ms.assetid: 3b48fd47-7397-4e2c-8bec-8157aa08978c
topic_type:
- apiref
ms.openlocfilehash: b4ae599a0e5cdb604fd9a610728671b39c67af31
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440898"
---
# <a name="imetadataemit-interface"></a>IMetaDataEmit-Schnittstelle
Stellt Methoden zum Erstellen, ändern und Speichern von Metadaten über die Assembly im aktuell definierten Bereich bereit. Die Metadaten können im Arbeitsspeicher gespeichert oder auf dem Datenträger gespeichert werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ApplyEditAndContinue-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)|Aktualisiert den aktuellen Assemblybereich mit den Änderungen, die im angegebenen `pImport`vorgenommen wurden.|  
|[DefineCustomAttribute-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)|Erstellt eine Definition für ein benutzerdefiniertes Attribut mit der angegebenen Metadatensignatur, das an das angegebene Objekt angefügt werden soll, und ruft ein Token für die Definition des benutzerdefinierten Attributs ab.|  
|[DefineEvent-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)|Erstellt eine Definition für ein Ereignis mit der angegebenen Metadatensignatur und ruft ein Token für diese Ereignis Definition ab.|  
|[DefineField-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definefield-method.md)|Erstellt eine Definition für ein Feld mit der angegebenen Metadatensignatur und ruft ein Token für diese Felddefinition ab.|  
|[DefineImportMember-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)|Erstellt eine Definition für einen Member eines Typs, der in einem Modul außerhalb des aktuellen Bereichs definiert ist, und ruft ein Token für diese Verweis Definition ab.|  
|[DefineImportType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)|Erstellt eine Definition für einen Verweis auf einen Typ, der in einem Modul außerhalb des aktuellen Bereichs definiert ist, und ruft ein Token für diese Verweis Definition ab.|  
|[DefineMemberRef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)|Erstellt eine Definition für einen Verweis auf einen Member eines Moduls außerhalb des aktuellen Bereichs und ruft ein Token für diese Verweis Definition ab.|  
|[DefineMethod-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)|Erstellt eine Definition für eine Methode mit der angegebenen Signatur und gibt ein Token an diese Methoden Definition zurück.|  
|[DefineMethodImpl-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethodimpl-method.md)|Erstellt eine Definition für die Implementierung einer Methode, die von einer Schnittstelle geerbt wurde, und gibt ein Token an diese Methoden Implementierungs Definition zurück.|  
|[DefineModuleRef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)|Erstellt die Metadatensignatur für ein Modul mit dem angegebenen Namen.|  
|[DefineNestedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definenestedtype-method.md)|Erstellt die Metadatensignatur einer Typdefinition und gibt ein `mdTypeDef` Token für diesen Typ zurück. Außerdem wird angegeben, dass der definierte Typ ein Member des Typs ist, auf den `tdEncloser`verweist.|  
|[DefineParam-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)|Erstellt eine Parameterdefinition mit der angegebenen Signatur für die Methode, auf die durch das angegebene Token verwiesen wird, und ruft ein Token für diese Parameterdefinition ab.|  
|[DefinePermissionSet-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)|Erstellt eine Definition für einen Berechtigungs Satz mit der angegebenen Metadatensignatur und ruft ein Token für diese Berechtigungs Satz Definition ab.|  
|[DefinePinvokeMap-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)|Legt die Features der PInvoke-Signatur der Methode fest, auf die durch das angegebene Token verwiesen wird.|  
|[DefineProperty-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)|Erstellt eine Eigenschafts Definition für den angegebenen Typ mit dem angegebenen `get` und `set` Methodenaccessoren und ruft ein Token für diese Eigenschafts Definition ab.|  
|[DefineSecurityAttributeSet-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definesecurityattributeset-method.md)|Erstellt einen Satz von Sicherheits Berechtigungen zum Anfügen an das Objekt, auf das durch das angegebene Token verwiesen wird.|  
|[DefineTypeDef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)|Erstellt eine Typdefinition für einen Common Language Runtime Typ und ruft ein Metadatentoken für diese Typdefinition ab.|  
|[DefineTypeRefByName-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)|Ruft ein Metadatentoken für einen Typ ab, der in einem anderen Modul außerhalb des aktuellen Bereichs definiert ist.|  
|[DefineUserString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)|Ruft ein Metadatentoken für die angegebene Literalzeichenfolge ab.|  
|[DeleteClassLayout-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deleteclasslayout-method.md)|Zerstört die klassenlayoutmetadatensignatur für den Typ, auf den vom angegebenen Token verwiesen wird.|  
|[DeleteFieldMarshal-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletefieldmarshal-method.md)|Zerstört die PInvoke-marshallingmetadatensignatur für das Objekt, auf das durch das angegebene Token verwiesen wird.|  
|[DeletePinvokeMap-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletepinvokemap-method.md)|Zerstört die PInvoke-Zuordnungsmetadaten für das Objekt, auf das durch das angegebene Token verwiesen wird.|  
|[DeleteToken-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletetoken-method.md)|Löscht das angegebene Token aus dem aktuellen Metadatenbereich.|  
|[GetSaveSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-getsavesize-method.md)|Ruft die geschätzte binäre Größe der Assembly im aktuellen Bereich ab.|  
|[GetTokenFromSig-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)|Ruft ein Token für die angegebene Metadatensignatur ab.|  
|[GetTokenFromTypeSpec-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)|Ruft ein Metadatentoken für den Typ mit der angegebenen Metadatensignatur ab.|  
|[Merge-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)|Fügt der Liste der zusammen zuführenden Bereiche den angegebenen importierten Bereich hinzu.|  
|[MergeEnd-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)|Führt alle Metadatenbereiche, die durch einen oder mehrere vorherige Aufrufe `IMetaDataEmit::Merge`angegeben werden, in den aktuellen Gültigkeitsbereich zusammen.|  
|[Save-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-save-method.md)|Speichert alle Metadaten im aktuellen Gültigkeitsbereich in der Datei an der angegebenen Adresse.|  
|[SaveToMemory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)|Speichert alle Metadaten im aktuellen Gültigkeitsbereich im angegebenen Speicherbereich.|  
|[SaveToStream-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)|Speichert alle Metadaten im aktuellen Gültigkeitsbereich in der angegebenen `IStream`.|  
|[SetClassLayout-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)|Legt die Klassenlayoutsignatur eines Typs fest, der durch einen früheren `IMetaDataEmit::DefineTypeDef`aufgerufen wird, oder aktualisiert diese.|  
|[SetCustomAttributeValue-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setcustomattributevalue-method.md)|Legt den Wert eines benutzerdefinierten Attributs fest, das durch einen vorherigen-`IMetaDataEmit::DefineCustomAttribute`definiert ist, oder aktualisiert diesen.|  
|[SetEventProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-seteventprops-method.md)|Legt die angegebene Funktion eines Ereignisses fest, das durch einen vorherigen-`IMetaDataEmit::DefineEvent`definiert ist, oder aktualisiert diese.|  
|[SetFieldMarshal-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldmarshal-method.md)|Legt die PInvoke-Marshallinginformationen für das Feld, die Methoden Rückgabe oder den Methoden Parameter fest, auf den vom angegebenen Token verwiesen wird.|  
|[SetFieldProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldprops-method.md)|Legt den Standardwert für das Feld fest, auf das durch das angegebene Feld Token verwiesen wird, oder aktualisiert dieses.|  
|[SetFieldRVA-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldrva-method.md)|Legt einen globalen Variablen Wert für die relative virtuelle Adresse des Felds fest, auf das durch das angegebene Token verwiesen wird.|  
|[SetHandler-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)|Legt die Methode, auf die der angegebene `IUnknown` Zeiger verweist, als Benachrichtigungs Rückruf für die Tokenneuzuordnung fest.|  
|[SetMethodImplFlags-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)|Legt die Metadatensignatur der geerbten Methoden Implementierung fest, auf die vom angegebenen Token verwiesen wird, oder aktualisiert sie.|  
|[SetMethodProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodprops-method.md)|Legt die Funktion, die bei der angegebenen relativen virtuellen Adresse gespeichert ist, für eine Methode fest, die durch einen vorherigen `IMetaDataEmit::DefineMethod`aufgerufen wird, oder aktualisiert sie.|  
|[SetModuleProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)|Aktualisiert Verweise auf ein Modul, das durch einen vorherigen-`IMetaDataEmit::DefineModuleRef`definiert wurde.|  
|[SetParamProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)|Legt die Features eines Methoden Parameters fest, der durch einen vorherigen `IMetaDataEmit::DefineParam`aufgerufen wurde, oder ändert Sie.|  
|[SetParent-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparent-method.md)|Legt fest, dass das angegebene Element, wie durch einen vorherigen-`IMetaDataEmit::DefineMemberRef`definiert, ein Member des angegebenen Typs ist, wie durch einen vorherigen-`IMetaDataEmit::DefineTypeDef`definiert.|  
|[SetPermissionSetProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpermissionsetprops-method.md)|Legt die Features der Metadatensignatur eines Berechtigungs Satzes fest oder aktualisiert diese, der durch einen vorherigen-`IMetaDataEmit::DefinePermissionSet`definiert wurde.|  
|[SetPinvokeMap-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpinvokemap-method.md)|Legt die Features der PInvoke-Signatur einer Methode fest, die durch einen früheren `IMetaDataEmit::DefinePinvokeMap`aufgerufen wird, oder ändert Sie.|  
|[SetPropertyProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpropertyprops-method.md)|Legt die in den Metadaten gespeicherten Features für eine Eigenschaft fest, die durch einen vorherigen-`IMetaDataEmit::DefineProperty`definiert wurde.|  
|[SetRVA-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)|Legt die relative virtuelle Adresse der angegebenen Methode fest.|  
|[SetTypeDefProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-settypedefprops-method.md)|Legt Funktionen eines Typs fest, der durch einen vorherigen-`IMetaDataEmit::DefineTypeDef`definiert wird.|  
|[TranslateSigWithScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-translatesigwithscope-method.md)|Importiert eine Assembly in den aktuellen Gültigkeitsbereich und ruft eine neue Metadatensignatur für den zusammengeführten Bereich ab.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
