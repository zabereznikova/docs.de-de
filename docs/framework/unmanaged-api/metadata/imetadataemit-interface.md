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
ms.openlocfilehash: a2c2512abc28f0140fc261c5136c7e1255db96de
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009210"
---
# <a name="imetadataemit-interface"></a>IMetaDataEmit-Schnittstelle
Stellt Methoden zum Erstellen, ändern und Speichern von Metadaten über die Assembly im aktuell definierten Bereich bereit. Die Metadaten können im Arbeitsspeicher gespeichert oder auf dem Datenträger gespeichert werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ApplyEditAndContinue-Methode](imetadataemit-applyeditandcontinue-method.md)|Aktualisiert den aktuellen Assemblybereich mit den Änderungen, die im angegebenen vorgenommen wurden `pImport` .|  
|[DefineCustomAttribute-Methode](imetadataemit-definecustomattribute-method.md)|Erstellt eine Definition für ein benutzerdefiniertes Attribut mit der angegebenen Metadatensignatur, das an das angegebene Objekt angefügt werden soll, und ruft ein Token für die Definition des benutzerdefinierten Attributs ab.|  
|[DefineEvent-Methode](imetadataemit-defineevent-method.md)|Erstellt eine Definition für ein Ereignis mit der angegebenen Metadatensignatur und ruft ein Token für diese Ereignis Definition ab.|  
|[DefineField-Methode](imetadataemit-definefield-method.md)|Erstellt eine Definition für ein Feld mit der angegebenen Metadatensignatur und ruft ein Token für diese Felddefinition ab.|  
|[DefineImportMember-Methode](imetadataemit-defineimportmember-method.md)|Erstellt eine Definition für einen Member eines Typs, der in einem Modul außerhalb des aktuellen Bereichs definiert ist, und ruft ein Token für diese Verweis Definition ab.|  
|[DefineImportType-Methode](imetadataemit-defineimporttype-method.md)|Erstellt eine Definition für einen Verweis auf einen Typ, der in einem Modul außerhalb des aktuellen Bereichs definiert ist, und ruft ein Token für diese Verweis Definition ab.|  
|[DefineMemberRef-Methode](imetadataemit-definememberref-method.md)|Erstellt eine Definition für einen Verweis auf einen Member eines Moduls außerhalb des aktuellen Bereichs und ruft ein Token für diese Verweis Definition ab.|  
|[DefineMethod-Methode](imetadataemit-definemethod-method.md)|Erstellt eine Definition für eine Methode mit der angegebenen Signatur und gibt ein Token an diese Methoden Definition zurück.|  
|[DefineMethodImpl-Methode](imetadataemit-definemethodimpl-method.md)|Erstellt eine Definition für die Implementierung einer Methode, die von einer Schnittstelle geerbt wurde, und gibt ein Token an diese Methoden Implementierungs Definition zurück.|  
|[DefineModuleRef-Methode](imetadataemit-definemoduleref-method.md)|Erstellt die Metadatensignatur für ein Modul mit dem angegebenen Namen.|  
|[DefineNestedType-Methode](imetadataemit-definenestedtype-method.md)|Erstellt die Metadatensignatur einer Typdefinition und gibt ein `mdTypeDef` Token für diesen Typ zurück. Außerdem wird angegeben, dass der definierte Typ ein Member des Typs ist, auf den von verwiesen wird `tdEncloser` .|  
|[DefineParam-Methode](imetadataemit-defineparam-method.md)|Erstellt eine Parameterdefinition mit der angegebenen Signatur für die Methode, auf die durch das angegebene Token verwiesen wird, und ruft ein Token für diese Parameterdefinition ab.|  
|[DefinePermissionSet-Methode](imetadataemit-definepermissionset-method.md)|Erstellt eine Definition für einen Berechtigungs Satz mit der angegebenen Metadatensignatur und ruft ein Token für diese Berechtigungs Satz Definition ab.|  
|[DefinePinvokeMap-Methode](imetadataemit-definepinvokemap-method.md)|Legt die Features der PInvoke-Signatur der Methode fest, auf die durch das angegebene Token verwiesen wird.|  
|[DefineProperty-Methode](imetadataemit-defineproperty-method.md)|Erstellt eine Eigenschafts Definition für den angegebenen Typ mit dem angegebenen `get` und den `set` Methoden Accessoren und ruft ein Token für diese Eigenschafts Definition ab.|  
|[DefineSecurityAttributeSet-Methode](imetadataemit-definesecurityattributeset-method.md)|Erstellt einen Satz von Sicherheits Berechtigungen zum Anfügen an das Objekt, auf das durch das angegebene Token verwiesen wird.|  
|[DefineTypeDef-Methode](imetadataemit-definetypedef-method.md)|Erstellt eine Typdefinition für einen Common Language Runtime Typ und ruft ein Metadatentoken für diese Typdefinition ab.|  
|[DefineTypeRefByName-Methode](imetadataemit-definetyperefbyname-method.md)|Ruft ein Metadatentoken für einen Typ ab, der in einem anderen Modul außerhalb des aktuellen Bereichs definiert ist.|  
|[DefineUserString-Methode](imetadataemit-defineuserstring-method.md)|Ruft ein Metadatentoken für die angegebene Literalzeichenfolge ab.|  
|[DeleteClassLayout-Methode](imetadataemit-deleteclasslayout-method.md)|Zerstört die klassenlayoutmetadatensignatur für den Typ, auf den vom angegebenen Token verwiesen wird.|  
|[DeleteFieldMarshal-Methode](imetadataemit-deletefieldmarshal-method.md)|Zerstört die PInvoke-marshallingmetadatensignatur für das Objekt, auf das durch das angegebene Token verwiesen wird.|  
|[DeletePinvokeMap-Methode](imetadataemit-deletepinvokemap-method.md)|Zerstört die PInvoke-Zuordnungsmetadaten für das Objekt, auf das durch das angegebene Token verwiesen wird.|  
|[DeleteToken-Methode](imetadataemit-deletetoken-method.md)|Löscht das angegebene Token aus dem aktuellen Metadatenbereich.|  
|[GetSaveSize-Methode](imetadataemit-getsavesize-method.md)|Ruft die geschätzte binäre Größe der Assembly im aktuellen Bereich ab.|  
|[GetTokenFromSig-Methode](imetadataemit-gettokenfromsig-method.md)|Ruft ein Token für die angegebene Metadatensignatur ab.|  
|[GetTokenFromTypeSpec-Methode](imetadataemit-gettokenfromtypespec-method.md)|Ruft ein Metadatentoken für den Typ mit der angegebenen Metadatensignatur ab.|  
|[Merge-Methode](imetadataemit-merge-method.md)|Fügt der Liste der zusammen zuführenden Bereiche den angegebenen importierten Bereich hinzu.|  
|[MergeEnd-Methode](imetadataemit-mergeend-method.md)|Führt alle Metadatenbereiche, die durch einen oder mehrere vorherige Aufrufe von angegeben werden, in den aktuellen Bereich zusammen `IMetaDataEmit::Merge` .|  
|[Save-Methode](imetadataemit-save-method.md)|Speichert alle Metadaten im aktuellen Gültigkeitsbereich in der Datei an der angegebenen Adresse.|  
|[SaveToMemory-Methode](imetadataemit-savetomemory-method.md)|Speichert alle Metadaten im aktuellen Gültigkeitsbereich im angegebenen Speicherbereich.|  
|[SaveToStream-Methode](imetadataemit-savetostream-method.md)|Speichert alle Metadaten im aktuellen Gültigkeitsbereich in der angegebenen `IStream` .|  
|[SetClassLayout-Methode](imetadataemit-setclasslayout-method.md)|Legt die Klassenlayoutsignatur eines Typs fest, der durch einen vorherigen-Befehl definiert ist, oder aktualisiert diese `IMetaDataEmit::DefineTypeDef` .|  
|[SetCustomAttributeValue-Methode](imetadataemit-setcustomattributevalue-method.md)|Legt den Wert eines benutzerdefinierten Attributs fest, das durch einen vorherigen-Befehl definiert ist, oder aktualisiert diesen `IMetaDataEmit::DefineCustomAttribute` .|  
|[SetEventProps-Methode](imetadataemit-seteventprops-method.md)|Legt die angegebene Funktion eines Ereignisses fest, das durch einen vorherigen-Aufrufwert definiert wird, oder aktualisiert diese `IMetaDataEmit::DefineEvent` .|  
|[SetFieldMarshal-Methode](imetadataemit-setfieldmarshal-method.md)|Legt die PInvoke-Marshallinginformationen für das Feld, die Methoden Rückgabe oder den Methoden Parameter fest, auf den vom angegebenen Token verwiesen wird.|  
|[SetFieldProps-Methode](imetadataemit-setfieldprops-method.md)|Legt den Standardwert für das Feld fest, auf das durch das angegebene Feld Token verwiesen wird, oder aktualisiert dieses.|  
|[SetFieldRVA-Methode](imetadataemit-setfieldrva-method.md)|Legt einen globalen Variablen Wert für die relative virtuelle Adresse des Felds fest, auf das durch das angegebene Token verwiesen wird.|  
|[SetHandler-Methode](imetadataemit-sethandler-method.md)|Legt die Methode, auf die der angegebene Zeiger verweist, `IUnknown` als Benachrichtigungs Rückruf für die Tokenneuzuordnung fest.|  
|[SetMethodImplFlags-Methode](imetadataemit-setmethodimplflags-method.md)|Legt die Metadatensignatur der geerbten Methoden Implementierung fest, auf die vom angegebenen Token verwiesen wird, oder aktualisiert sie.|  
|[SetMethodProps-Methode](imetadataemit-setmethodprops-method.md)|Legt die Funktion, die bei der angegebenen relativen virtuellen Adresse gespeichert ist, für eine durch einen vorherigen-Befehl definierte Methode fest oder aktualisiert Sie `IMetaDataEmit::DefineMethod` .|  
|[SetModuleProps-Methode](imetadataemit-setmoduleprops-method.md)|Aktualisiert Verweise auf ein Modul, das durch einen vorherigen-Befehl definiert wurde `IMetaDataEmit::DefineModuleRef` .|  
|[SetParamProps-Methode](imetadataemit-setparamprops-method.md)|Legt Funktionen eines Methoden Parameters fest, der durch einen vorherigen-Aufrufwert definiert wurde, oder ändert diese `IMetaDataEmit::DefineParam` .|  
|[SetParent-Methode](imetadataemit-setparent-method.md)|Legt fest, dass der angegebene Member, wie durch einen vorherigen-Aufrufwert definiert, `IMetaDataEmit::DefineMemberRef` ein Member des angegebenen Typs ist, wie durch einen vorherigen-Befehl definiert `IMetaDataEmit::DefineTypeDef` .|  
|[SetPermissionSetProps-Methode](imetadataemit-setpermissionsetprops-method.md)|Legt die Features der Metadatensignatur eines Berechtigungs Satzes fest oder aktualisiert Sie, der durch einen vorherigen-Aufrufvorgang definiert wurde `IMetaDataEmit::DefinePermissionSet` .|  
|[SetPinvokeMap-Methode](imetadataemit-setpinvokemap-method.md)|Legt die Features der PInvoke-Signatur einer Methode fest, wie durch einen vorherigen-Aufrufwert definiert, oder ändert Sie `IMetaDataEmit::DefinePinvokeMap` .|  
|[SetPropertyProps-Methode](imetadataemit-setpropertyprops-method.md)|Legt die in den Metadaten gespeicherten Funktionen für eine Eigenschaft fest, die durch einen vorherigen-Aufrufvorgang definiert wird `IMetaDataEmit::DefineProperty` .|  
|[SetRVA-Methode](imetadataemit-setrva-method.md)|Legt die relative virtuelle Adresse der angegebenen Methode fest.|  
|[SetTypeDefProps-Methode](imetadataemit-settypedefprops-method.md)|Legt Funktionen eines Typs fest, der durch einen vorherigen-Aufrufwert definiert wird `IMetaDataEmit::DefineTypeDef` .|  
|[TranslateSigWithScope-Methode](imetadataemit-translatesigwithscope-method.md)|Importiert eine Assembly in den aktuellen Gültigkeitsbereich und ruft eine neue Metadatensignatur für den zusammengeführten Bereich ab.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](metadata-interfaces.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
