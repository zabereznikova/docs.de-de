---
title: IMetaDataEmit-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit
helpviewer_keywords: IMetaDataEmit interface [.NET Framework metadata]
ms.assetid: 3b48fd47-7397-4e2c-8bec-8157aa08978c
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 856b4c42b018d6b1cefe6b61e21a15e7212f9541
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit-interface"></a>IMetaDataEmit-Schnittstelle
Stellt Methoden zum Erstellen, ändern und Speichern von Metadaten über die Assembly im momentan definierten Bereich. Die Metadaten kann im Arbeitsspeicher gespeichert oder auf dem Datenträger gespeichert werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ApplyEditAndContinue-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)|Aktualisiert den aktuellen assemblygültigkeitsbereich mit den Änderungen in der angegebenen `pImport`.|  
|[DefineCustomAttribute-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)|Erstellt eine Definition für ein benutzerdefiniertes Attribut mit der angegebenen Metadaten-Signatur, die an das angegebene Objekt angefügt werden, und ruft ein Token für diese Definition des benutzerdefinierten Attributs ab.|  
|[DefineEvent-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)|Erstellt eine Definition für ein Ereignis mit der angegebenen Metadatensignatur und ruft ein Token für die Ereignisdefinition ab.|  
|[DefineField-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definefield-method.md)|Erstellt eine Definition für ein Feld mit der angegebenen Metadatensignatur und ruft ein Token, Field-Definition ab.|  
|[DefineImportMember-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)|Erstellt eine Definition für einen Member eines Typs, das in einem Modul außerhalb des aktuellen Bereichs definiert ist, und ruft ein Token für diese Verweisdefinition ab.|  
|[DefineImportType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)|Erstellt eine Definition für einen Verweis auf einen Typ, der in einem Modul außerhalb des aktuellen Bereichs definiert ist, und ruft ein Token für diese Verweisdefinition ab.|  
|[DefineMemberRef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)|Erstellt eine Definition für einen Verweis auf einen Member eines Moduls außerhalb des aktuellen Bereichs und ruft ein Token für diese Verweisdefinition ab.|  
|[DefineMethod-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)|Erstellt eine Definition für eine Methode mit der angegebenen Signatur und gibt ein Token für diese Methodendefinition zurück.|  
|[DefineMethodImpl-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethodimpl-method.md)|Erstellt eine Definition für die Implementierung einer Methode, die von einer Schnittstelle geerbt, und gibt ein Token zu dieser Definition der Implementierung der Methode zurück.|  
|[DefineModuleRef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)|Erstellt die Metadatensignatur für ein Modul mit dem angegebenen Namen.|  
|[DefineNestedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definenestedtype-method.md)|Erstellt die Metadatensignatur einer Typdefinition und gibt ein `mdTypeDef` token für diesen Typ, außerdem fest, dass der definierte Typ ein Member des Typs verweist `tdEncloser`.|  
|[DefineParam-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)|Erstellt eine Parameterdefinition mit der angegebenen Signatur für die Methode, die durch das angegebene Token verwiesen wird, und ruft ein Token für die Parameterdefinition.|  
|[DefinePermissionSet-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)|Erstellt eine Definition für einen Berechtigungssatz, der mit der angegebenen Metadatensignatur und ruft ein Token für diese Berechtigungssatzdefinition ab.|  
|[DefinePinvokeMap-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)|Legt die Features eines PInvoke-Signatur der Methode auf, die durch das angegebene Token verwiesen wird.|  
|[DefineProperty-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)|Erstellt eine Eigenschaftsdefinition für den angegebenen Typ mit dem angegebenen `get` und `set` Methodenaccessoren und ruft ein Token auf, Eigenschaftsdefinition ab.|  
|[DefineSecurityAttributeSet-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definesecurityattributeset-method.md)|Erstellt einen Satz von Sicherheitsberechtigungen für die Verbindung mit dem Objekt, das durch das angegebene Token verwiesen wird.|  
|[DefineTypeDef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)|Erstellt eine Typdefinition für einen Typ der common Language Runtime und ruft ein Metadatentoken für die Typdefinition.|  
|[DefineTypeRefByName-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)|Ruft ein Metadatentoken für einen Typ, der in einem anderen Modul außerhalb des aktuellen Bereichs definiert ist.|  
|[DefineUserString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)|Ruft ein Metadatentoken für das angegebene Zeichenfolgenliteral.|  
|[DeleteClassLayout-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deleteclasslayout-method.md)|Zerstört die Metadatensignatur Layout für den Typ, der durch das angegebene Token verwiesen wird.|  
|[DeleteFieldMarshal-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletefieldmarshal-method.md)|Zerstört die PInvoke Marshalling Metadatensignatur für das Objekt, das durch das angegebene Token verwiesen wird.|  
|[DeletePinvokeMap-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletepinvokemap-method.md)|Zerstört die Zuordnungsmetadaten PInvoke für das Objekt, das durch das angegebene Token verwiesen wird.|  
|[DeleteToken-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletetoken-method.md)|Löscht das angegebene Token aus dem aktuellen Metadatenbereich.|  
|[GetSaveSize-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-getsavesize-method.md)|Ruft die geschätzte binäre Größe der Assembly im aktuellen Bereich ab.|  
|[GetTokenFromSig-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)|Ruft ein Token für die angegebene Metadatensignatur ab.|  
|[GetTokenFromTypeSpec-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)|Ruft ein Metadatentoken für den Typ mit der angegebenen Metadaten-Signatur.|  
|[Merge-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)|Die Liste der zusammenzuführenden Bereiche hinzugefügt im angegebenen importierten Bereich.|  
|[MergeEnd-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)|Führt den aktuellen Bereich alle Metadatenbereiche, die durch eine oder mehrere vorherigen Aufrufe von angegeben `IMetaDataEmit::Merge`.|  
|[Save-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-save-method.md)|Speichert alle Metadaten im aktuellen Bereich für die Datei an der angegebenen Adresse an.|  
|[SaveToMemory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)|Speichert alle Metadaten im aktuellen Bereich für den angegebenen Bereich des Arbeitsspeichers.|  
|[SaveToStream-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)|Speichert alle Metadaten im aktuellen Bereich für den angegebenen `IStream`.|  
|[SetClassLayout-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)|Legt fest oder aktualisiert die Klassensignatur Layout eines Typs, der durch einen vorherigen Aufruf von definiert `IMetaDataEmit::DefineTypeDef`.|  
|[SetCustomAttributeValue-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setcustomattributevalue-method.md)|Legt fest oder aktualisiert den Wert eines benutzerdefinierten Attributs definiert, die durch einen vorherigen Aufruf von `IMetaDataEmit::DefineCustomAttribute`.|  
|[SetEventProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-seteventprops-method.md)|Legt fest oder aktualisiert die angegebene Funktion eines Ereignisses definiert, die durch einen vorherigen Aufruf von `IMetaDataEmit::DefineEvent`.|  
|[SetFieldMarshal-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldmarshal-method.md)|Legt die PInvoke Marshallinginformationen für den Parameter Feld,-Methodenrückgabe oder eine Methode, die durch das angegebene Token verwiesen wird.|  
|[SetFieldProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldprops-method.md)|Legt fest oder aktualisiert den Standardwert für das Feld auf die durch das angegebene Feld-Token verwiesen wird.|  
|[SetFieldRVA-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldrva-method.md)|Legt einen globalen Variablenwert für die relative virtuelle Adresse des Felds auf die durch das angegebene Token verwiesen wird.|  
|[SetHandler-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)|Legt die Methode, die auf die verwiesen wird durch das angegebene `IUnknown` Zeiger als eines Rückrufs für token neue Zuordnungen.|  
|[SetMethodImplFlags-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)|Legt fest oder aktualisiert die Metadatensignatur der Implementierung geerbte Methode auf, die durch das angegebene Token verwiesen wird.|  
|[SetMethodProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodprops-method.md)|Legt fest oder aktualisiert das Feature "" an der angegebenen relativen virtuellen Adresse, einer Methode, die durch einen vorherigen Aufruf definierten gespeicherte `IMetaDataEmit::DefineMethod`.|  
|[SetModuleProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)|Aktualisiert die Verweise auf ein Modul, das durch einen vorherigen Aufruf definierten `IMetaDataEmit::DefineModuleRef`.|  
|[SetParamProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)|Legt fest oder ändert die Features eines Methodenparameters, die durch einen vorherigen Aufruf definiert wurde `IMetaDataEmit::DefineParam`.|  
|[SetParent-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparent-method.md)|Legt fest, dass die angegebenen Member auf, wie er durch einen vorherigen Aufruf `IMetaDataEmit::DefineMemberRef`, ist ein Member des angegebenen Typs gemäß der Definition von einem vorherigen Aufruf für `IMetaDataEmit::DefineTypeDef`.|  
|[SetPermissionSetProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpermissionsetprops-method.md)|Legt fest oder aktualisiert Sie Features der Metadatensignatur der einen Berechtigungssatz, der durch einen vorherigen Aufruf definierten `IMetaDataEmit::DefinePermissionSet`.|  
|[SetPinvokeMap-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpinvokemap-method.md)|Legt fest oder ändert Sie Funktionen von PInvoke-Signatur einer Methode, gemäß der Definition von einem vorherigen Aufruf für `IMetaDataEmit::DefinePinvokeMap`.|  
|[SetPropertyProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpropertyprops-method.md)|Legt die Funktionen, die in den Metadaten für eine Eigenschaft, die definiert, die durch einen vorherigen Aufruf von gespeicherten `IMetaDataEmit::DefineProperty`.|  
|[SetRVA-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)|Legt die relative virtuelle Adresse der angegebenen Methode fest.|  
|[SetTypeDefProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-settypedefprops-method.md)|Legt die Funktionen eines Typs, der durch einen vorherigen Aufruf von definiert `IMetaDataEmit::DefineTypeDef`.|  
|[TranslateSigWithScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-translatesigwithscope-method.md)|Importiert eine Assembly in den aktuellen Bereich und ruft eine neue Metadatensignatur für den zusammengeführten Bereich ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
