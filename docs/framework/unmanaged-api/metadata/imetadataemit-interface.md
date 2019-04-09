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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 10942541b781d367820301588656b2f1fc2fd006
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184417"
---
# <a name="imetadataemit-interface"></a>IMetaDataEmit-Schnittstelle
Stellt Methoden zum Erstellen, ändern und Speichern von Metadaten über die Assembly im momentan definierten Bereich. Die Metadaten im Arbeitsspeicher gespeichert, oder auf dem Datenträger gespeichert werden kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ApplyEditAndContinue-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)|Aktualisiert den aktuellen Assemblybereich mit den Änderungen in der angegebenen `pImport`.|  
|[DefineCustomAttribute-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)|Erstellt eine Definition für ein benutzerdefiniertes Attribut mit der angegebenen Metadaten-Signatur, die an das angegebene Objekt angefügt werden, und ruft ein Token für diese Definition des benutzerdefinierten Attributs ab.|  
|[DefineEvent-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)|Erstellt eine Definition für ein Ereignis mit der angegebenen Metadaten-Signatur und ruft ein Token für die Ereignisdefinition ab.|  
|[DefineField-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definefield-method.md)|Erstellt eine Definition für ein Feld mit der angegebenen Metadaten-Signatur und ruft ein Token, Field-Definition ab.|  
|[DefineImportMember-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)|Erstellt eine Definition für einen Member eines Typs, der in einem Modul außerhalb des aktuellen Bereichs definiert ist und ein Token für diese Verweisdefinition abruft.|  
|[DefineImportType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)|Erstellt eine Definition für einen Verweis auf einen Typ, der in einem Modul außerhalb des aktuellen Bereichs definiert ist und ruft ein Token für diese Verweisdefinition.|  
|[DefineMemberRef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)|Erstellt eine Definition für einen Verweis auf einen Member eines Moduls außerhalb des aktuellen Bereichs und ruft ein Token für diese Verweisdefinition.|  
|[DefineMethod-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)|Erstellt eine Definition für eine Methode mit der angegebenen Signatur und ein Token an dieser Methodendefinition zurück.|  
|[DefineMethodImpl-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethodimpl-method.md)|Erstellt eine Definition für die Implementierung einer Methode, die von einer Schnittstelle geerbt, und ein Token an dieser Definition der Implementierung der Methode zurück.|  
|[DefineModuleRef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)|Erstellt die Signatur der Metadaten für ein Modul mit dem angegebenen Namen.|  
|[DefineNestedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definenestedtype-method.md)|Erstellt die Metadatensignatur der Definition eines Typs und gibt eine `mdTypeDef` token für diesen Typ, der außerdem fest, dass der definierte Typ ein Member des Typs verweist `tdEncloser`.|  
|[DefineParam-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)|Erstellt eine Parameterdefinition mit der angegebenen Signatur für die Methode auf, die durch das angegebene Token verwiesen wird und ruft ein Token für diese Parameterdefinition ab.|  
|[DefinePermissionSet-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)|Erstellt eine Definition für einen Berechtigungssatz, der mit der angegebenen Metadaten-Signatur und ruft ein Token für die Definition dieser Berechtigung Menge ab.|  
|[DefinePinvokeMap-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)|Legt die Funktionen von PInvoke-Signatur der Methode auf, die durch das angegebene Token verwiesen wird.|  
|[DefineProperty-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)|Erstellt eine Eigenschaftsdefinition für den angegebenen Typ, mit dem angegebenen `get` und `set` Methodenaccessoren, und ruft ein Token auf diese Eigenschaftsdefinition ab.|  
|[DefineSecurityAttributeSet-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definesecurityattributeset-method.md)|Erstellt einen Satz von Sicherheitsberechtigungen für das Anfügen an das Objekt, das durch das angegebene Token verwiesen wird.|  
|[DefineTypeDef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)|Erstellt eine Typdefinition für einen Typ der common Language Runtime und ruft ein Metadatentoken für die Typdefinition.|  
|[DefineTypeRefByName-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)|Ruft Metadaten für einen Typ, der in einem anderen Modul außerhalb des aktuellen Bereichs definiert ist ab.|  
|[DefineUserString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)|Ruft Metadaten für die angegebene Zeichenfolge ab.|  
|[DeleteClassLayout-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deleteclasslayout-method.md)|Zerstört die Metadatensignatur Layout für den Typ auf, die durch das angegebene Token verwiesen wird.|  
|[DeleteFieldMarshal-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletefieldmarshal-method.md)|Zerstört die PInvoke Marshalling der Signatur der Metadaten für das Objekt, das durch das angegebene Token verwiesen wird.|  
|[DeletePinvokeMap-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletepinvokemap-method.md)|Zerstört die PInvoke-Mapping-Metadaten für das Objekt, das durch das angegebene Token verwiesen wird.|  
|[DeleteToken-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletetoken-method.md)|Löscht das angegebene Token aus der aktuellen Metadatenbereich.|  
|[GetSaveSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-getsavesize-method.md)|Ruft die binäre geschätzte Größe der Assembly im aktuellen Bereich ab.|  
|[GetTokenFromSig-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)|Ruft ein Token für die angegebenen Metadaten-Signatur ab.|  
|[GetTokenFromTypeSpec-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)|Ruft Metadaten für den Typ mit der angegebenen Metadaten-Signatur ab.|  
|[Merge-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)|Fügt im angegebenen importierten Bereich der Liste der Bereiche zusammengeführt werden sollen.|  
|[MergeEnd-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)|Merges im aktuellen Bereich alle Metadatenbereiche, die durch eine oder mehrere früheren aufrufen angegeben `IMetaDataEmit::Merge`.|  
|[Save-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-save-method.md)|Speichert alle Metadaten im aktuellen Bereich in die Datei an der angegebenen Adresse an.|  
|[SaveToMemory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)|Speichert alle Metadaten im aktuellen Bereich in den angegebenen Bereich des Arbeitsspeichers an.|  
|[SaveToStream-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)|Speichert alle Metadaten im aktuellen Bereich für den angegebenen `IStream`.|  
|[SetClassLayout-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)|Legt fest oder aktualisiert die Signatur eines Typs, definiert durch einen vorherigen Aufruf von Layout `IMetaDataEmit::DefineTypeDef`.|  
|[SetCustomAttributeValue-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setcustomattributevalue-method.md)|Legt fest oder aktualisiert den Wert eines benutzerdefinierten Attributs definiert, die von einem vorherigen Aufruf von `IMetaDataEmit::DefineCustomAttribute`.|  
|[SetEventProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-seteventprops-method.md)|Legt fest oder aktualisiert die angegebene Funktion eines Ereignisses definiert, die von einem vorherigen Aufruf von `IMetaDataEmit::DefineEvent`.|  
|[SetFieldMarshal-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldmarshal-method.md)|Legt die Marshallinginformationen für den Parameter Feld, Methode zurückgeben, oder eine Methode, die auf die verwiesen wird durch das angegebene Token PInvoke fest.|  
|[SetFieldProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldprops-method.md)|Legt fest oder aktualisiert den Standardwert für das Feld auf die durch das angegebene Feld-Token verwiesen wird.|  
|[SetFieldRVA-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldrva-method.md)|Legt einen Wert der globalen Variablen für die relative virtuelle Adresse des Felds auf die durch das angegebene Token verwiesen wird.|  
|[SetHandler-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)|Legt die Methode, die auf die verwiesen wird durch das angegebene `IUnknown` Zeiger als eines Rückrufs für token neuzuordnungen von Adressen.|  
|[SetMethodImplFlags-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)|Legt fest oder aktualisiert die Metadatensignatur der geerbten methodenimplementierung auf, die durch das angegebene Token verwiesen wird.|  
|[SetMethodProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodprops-method.md)|Legt fest oder aktualisiert die Funktion, die an der angegebenen relativen virtuellen Adresse, einer Methode, die von einem vorherigen Aufruf von definiert gespeicherte `IMetaDataEmit::DefineMethod`.|  
|[SetModuleProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)|Aktualisiert die Verweise auf ein Modul definiert, die von einem vorherigen Aufruf von `IMetaDataEmit::DefineModuleRef`.|  
|[SetParamProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)|Legt fest oder ändert Sie Features eines Methodenparameters, die von einem vorherigen Aufruf von definiert wurde `IMetaDataEmit::DefineParam`.|  
|[SetParent-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparent-method.md)|Legt fest, dass der angegebene Member, wie von einem vorherigen Aufruf von definiert `IMetaDataEmit::DefineMemberRef`, ist ein Mitglied über den angegebenen Typ, gemäß einem vorherigen Aufruf von `IMetaDataEmit::DefineTypeDef`.|  
|[SetPermissionSetProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpermissionsetprops-method.md)|Legt fest oder aktualisiert die Metadatensignatur der einen Berechtigungssatz auf, die von einem vorherigen Aufruf von definierten Funktionen `IMetaDataEmit::DefinePermissionSet`.|  
|[SetPinvokeMap-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpinvokemap-method.md)|Legt fest oder ändert Sie Features von PInvoke-Signatur einer Methode, gemäß einem vorherigen Aufruf von `IMetaDataEmit::DefinePinvokeMap`.|  
|[SetPropertyProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpropertyprops-method.md)|Legt die Funktionen, die in den Metadaten für eine Eigenschaft, die definiert, die von einem vorherigen Aufruf von gespeicherten `IMetaDataEmit::DefineProperty`.|  
|[SetRVA-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)|Legt fest, die relative virtuelle Adresse der angegebenen Methode.|  
|[SetTypeDefProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-settypedefprops-method.md)|Legt die Funktionen eines Typs, die von einem vorherigen Aufruf von definiert `IMetaDataEmit::DefineTypeDef`.|  
|[TranslateSigWithScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-translatesigwithscope-method.md)|Importiert eine Assembly in den aktuellen Bereich und ruft eine neue Metadatensignatur für den zusammengeführten Bereich.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
