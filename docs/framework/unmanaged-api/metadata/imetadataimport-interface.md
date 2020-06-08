---
title: IMetaDataImport-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport
helpviewer_keywords:
- IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0adbbd35-5e8d-4fec-8268-dc70a07c5975
topic_type:
- apiref
ms.openlocfilehash: 02d1ea1ef12fa158ce7ec94aeca4356ac54d4e5f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503483"
---
# <a name="imetadataimport-interface"></a>IMetaDataImport-Schnittstelle
Stellt Methoden zum Importieren und Bearbeiten vorhandener Metadaten aus einer portablen ausführbaren Datei (PE-Datei) oder einer anderen Quelle wie einer Typbibliothek oder einer eigenständigen Laufzeit-Metadatenbinärdatei bereit  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CloseEnum-Methode](imetadataimport-closeenum-method.md)|Schließt den Enumerator mit dem angegebenen Handle.|  
|[CountEnum-Methode](imetadataimport-countenum-method.md)|Ruft die Anzahl der Elemente im Enumerator mit dem angegebenen Handle ab.|  
|[EnumCustomAttributes-Methode](imetadataimport-enumcustomattributes-method.md)|Zählt eine Liste der benutzerdefinierten Attributdefinitionstoken mit dem angegebenen Typ oder Element auf.|  
|[EnumEvents-Methode](imetadataimport-enumevents-method.md)|Zählt Ereignisdefinitionstoken für das angegebene TypeDef-Token auf.|  
|[EnumFields-Methode](imetadataimport-enumfields-method.md)|Zählt FieldDef-Token für den Typ auf, auf den durch das angegebene TypeDef-Token verwiesen wird.|  
|[EnumFieldsWithName-Methode](imetadataimport-enumfieldswithname-method.md)|Zählt FieldDef-Token des angegebenen Typs mit dem angegebenen Namen auf.|  
|[EnumInterfaceImpls-Methode](imetadataimport-enuminterfaceimpls-method.md)|Zählt MethodDef-Token auf, die Schnittstellenimplementierungen darstellen.|  
|[EnumMemberRefs-Methode](imetadataimport-enummemberrefs-method.md)|Zählt MemberRef-Token auf, die Elemente des angegebenen Typs darstellen.|  
|[EnumMembers-Methode](imetadataimport-enummembers-method.md)|Zählt MemberDef-Token auf, die Elemente des angegebenen Typs darstellen.|  
|[EnumMembersWithName-Methode](imetadataimport-enummemberswithname-method.md)|Zählt MemberDef-Token auf, die Elemente des angegebenen Typs mit dem angegebenen Namen darstellen.|  
|[EnumMethodImpls-Methode](imetadataimport-enummethodimpls-method.md)|Zählt MethodBody- und MethodDeclaration-Token auf, die Methoden des angegebenen Typs darstellen.|  
|[EnumMethods-Methode](imetadataimport-enummethods-method.md)|Zählt MethodDef-Token auf, die Methoden des angegebenen Typs darstellen.|  
|[EnumMethodSemantics-Methode](imetadataimport-enummethodsemantics-method.md)|Zählt die Eigenschaften und die Eigenschaftenänderungsereignisse auf, auf die sich die angegebene Methode bezieht.|  
|[EnumMethodsWithName-Methode](imetadataimport-enummethodswithname-method.md)|Zählt Methoden auf, die den angegebenen Namen aufweisen und durch den Typ definiert sind, auf den durch das angegebene TypeDef-Token verwiesen wird.|  
|[EnumModuleRefs-Methode](imetadataimport-enummodulerefs-method.md)|Zählt ModuleRef-Token auf, die importierte Module darstellen.|  
|[EnumParams-Methode](imetadataimport-enumparams-method.md)|Zählt ParamDef-Token auf, die die Parameter der Methode darstellen, auf die vom angegebenen MethodDef-Token verwiesen wird.|  
|[EnumPermissionSets-Methode](imetadataimport-enumpermissionsets-method.md)|Zählt Berechtigungen für die Objekte in einem angegebenen Metadatenbereich auf.|  
|[EnumProperties-Methode](imetadataimport-enumproperties-method.md)|Zählt PropertyDef-Token auf, die die Eigenschaften des Typs darstellen, auf den vom angegebenen TypeDef-Token verwiesen wird.|  
|[EnumSignatures-Methode](imetadataimport-enumsignatures-method.md)|Zählt Signaturtoken auf, die eigenständige Signaturen im aktuellen Bereich darstellen.|  
|[EnumTypeDefs-Methode](imetadataimport-enumtypedefs-method.md)|Zählt TypeDef-Token auf, die alle Typen innerhalb des aktuellen Bereichs darstellen.|  
|[EnumTypeRefs-Methode](imetadataimport-enumtyperefs-method.md)|Zählt TypeRef-Token auf, die im aktuellen Metadatenbereich definiert sind.|  
|[EnumTypeSpecs-Methode](imetadataimport-enumtypespecs-method.md)|Zählt TypeSpec-Token auf, die im aktuellen Metadatenbereich definiert sind.|  
|[EnumUnresolvedMethods-Methode](imetadataimport-enumunresolvedmethods-method.md)|Zählt MemberDef-Token auf, die die nicht aufgelösten Methoden im aktuellen Metadatenbereich darstellen.|  
|[EnumUserStrings-Methode](imetadataimport-enumuserstrings-method.md)|Zählt String-Token auf, die hartcodierte Zeichenfolgen im aktuellen Metadatenbereich darstellen.|  
|[FindField-Methode](imetadataimport-findfield-method.md)|Ruft das FieldDef-Token für das Feld ab, das ein Element des angegebenen Typs ist und den angegebenen Namen und die Metadatensignatur aufweist.|  
|[FindMember-Methode](imetadataimport-findmember-method.md)|Ruft einen Zeiger auf das MemberDef-Token für das Element ab, das durch den angegebenen Typ mit dem angegebenen Namen und der Metadatensignatur definiert ist.|  
|[FindMemberRef-Methode](imetadataimport-findmemberref-method.md)|Ruft einen Zeiger auf das MemberRef-Token für das Element ab, das durch den angegebenen Typ mit dem angegebenen Namen und der Metadatensignatur definiert ist.|  
|[FindMethod-Methode](imetadataimport-findmethod-method.md)|Ruft einen Zeiger auf das MethodDef-Token für die Methode ab, die durch den angegebenen Typ mit dem angegebenen Namen und der Metadatensignatur definiert ist.|  
|[FindTypeDefByName-Methode](imetadataimport-findtypedefbyname-method.md)|Ruft einen Zeiger auf das TypeDef-Metadatentoken für den Typ mit dem angegebenen Namen ab.|  
|[FindTypeRef-Methode](imetadataimport-findtyperef-method.md)|Ruft einen Zeiger auf das TypeRef-Metadatentoken ab, das auf den Typ im angegebenen Suchbereich mit dem angegebenen Namen verweist.|  
|[GetClassLayout-Methode](imetadataimport-getclasslayout-method.md)|Ruft Layoutinformationen für die Klasse ab, auf die vom angegebenen TypeDef-Token verwiesen wird.|  
|[GetCustomAttributeByName-Methode](imetadataimport-getcustomattributebyname-method.md)|Ruft den Wert des benutzerdefinierten Attributs ab, wenn sein Name angegeben wurde.|  
|[GetCustomAttributeProps-Methode](imetadataimport-getcustomattributeprops-method.md)|Ruft den Wert des benutzerdefinierten Attributs ab, wenn sein Metadatentoken angegeben wurde.|  
|[GetEventProps-Methode](imetadataimport-geteventprops-method.md)|Ruft Metadateninformationen (z. B. den deklarierenden Typ, die Hinzufügungs- und Entfernungsmethoden für Delegaten und alle Kennzeichnungen und sonstigen zugeordneten Daten) für das Ereignis ab, das durch das angegebene Ereignistoken dargestellt wird.|  
|[GetFieldMarshal-Methode](imetadataimport-getfieldmarshal-method.md)|Ruft einen Zeiger auf den systemeigenen, nicht verwalteten Typ des Felds ab, das durch das angegebene Field-Metadatentoken dargestellt wird.|  
|[GetFieldProps-Methode](imetadataimport-getfieldprops-method.md)|Ruft Metadaten ab, die dem Feld zugeordnet sind, auf das durch das angegebene FieldDef-Token verwiesen wird.|  
|[GetInterfaceImplProps-Methode](imetadataimport-getinterfaceimplprops-method.md)|Ruft einen Zeiger auf die Metadatentoken für den Typ ab, der die angegebene Methode implementiert, und für die Schnittstelle, die diese Methode deklariert.|  
|[GetMemberProps-Methode](imetadataimport-getmemberprops-method.md)|Ruft Metadateninformationen (z. B. den Namen, die binäre Signatur und die relative virtuelle Adresse) des Typmelements ab, auf das durch das angegebene Metadatentoken verwiesen wird.|  
|[GetMemberRefProps-Methode](imetadataimport-getmemberrefprops-method.md)|Ruft Metadaten ab, die dem Element zugeordnet sind, auf das durch das angegebene Token verwiesen wird.|  
|[GetMethodProps-Methode](imetadataimport-getmethodprops-method.md)|Ruft die Metadaten ab, die der Methode zugeordnet sind, auf die durch das angegebene MethodDef-Token verwiesen wird.|  
|[GetMethodSemantics-Methode](imetadataimport-getmethodsemantics-method.md)|Ruft einen Zeiger auf die Beziehung zwischen der Methode ab, auf die vom angegebenen MethodDef-Token verwiesen wird, und der gepaarten Eigenschaft und dem Ereignis, auf die vom angegebenen EventProp-Token verwiesen wird.|  
|[GetModuleFromScope-Methode](imetadataimport-getmodulefromscope-method.md)|Ruft einen Zeiger auf das Metadatentoken für das Modul ab, auf das im aktuellen Metadatenbereich verwiesen wird.|  
|[GetModuleRefProps-Methode](imetadataimport-getmodulerefprops-method.md)|Ruft den Namen des Moduls ab, auf das vom angegebenen Metadatentoken verwiesen wird.|  
|[GetNameFromToken-Methode](imetadataimport-getnamefromtoken-method.md)|Ruft den UTF-8-Namen des Objekts ab, auf das vom angegebenen Metadatentoken verwiesen wird.|  
|[GetNativeCallConvFromSig-Methode](imetadataimport-getnativecallconvfromsig-method.md)|Ruft die systemeigene Aufrufkonvention für die Methode ab, die durch den angegebenen Signaturzeiger dargestellt wird.|  
|[GetNestedClassProps-Methode](imetadataimport-getnestedclassprops-method.md)|Ruft das TypeDef-Token für den einschließenden übergeordneten Typ des angegebenen geschachtelten Typs ab.|  
|[GetParamForMethodIndex-Methode](imetadataimport-getparamformethodindex-method.md)|Ruft einen Zeiger auf das Token ab, das den Parameter an der angegebenen Ordinalposition in der Sequenz der Methodenparameter für die Methode darstellt, die durch das angegebene MethodDef-Token dargestellt wird.|  
|[GetParamProps-Methode](imetadataimport-getparamprops-method.md)|Ruft Metadatenwerte für den Parameter ab, auf den durch das angegebene ParamDef-Token verwiesen wird.|  
|[GetPermissionSetProps-Methode](imetadataimport-getpermissionsetprops-method.md)|Ruft die Metadaten ab, die dem "System.Security.PermissionSet" zugeordnet sind, das durch das angegebene Berechtigungstoken dargestellt wird.|  
|[GetPinvokeMap](imetadataimport-getpinvokemap-method.md)|Ruft ein ModuleRef-Token zum Darstellen der Zielassembly eines PInvoke-Aufrufs ab.|  
|[GetPropertyProps-Methode](imetadataimport-getpropertyprops-method.md)|Ruft die Metadaten ab, die der Eigenschaft zugeordnet sind, die durch das angegebene Token dargestellt wird.|  
|[GetRVA-Methode](imetadataimport-getrva-method.md)|Ruft den Offset der relativen virtuellen Adresse des durch das angegebene Token dargestellten Codeobjekts ab.|  
|[GetScopeProps-Methode](imetadataimport-getscopeprops-method.md)|Ruft den Namen und optional den Versionsbezeichner der Assembly oder des Moduls im aktuellen Metadatenbereich ab.|  
|[GetSigFromToken-Methode](imetadataimport-getsigfromtoken-method.md)|Ruft die binäre Metadatensignatur ab, die dem angegebenen Token zugeordnet ist.|  
|[GetTypeDefProps-Methode](imetadataimport-gettypedefprops-method.md)|Gibt Metadateninformationen für den Typ zurück, der durch das angegebene TypeDef-Token dargestellt wird.|  
|[GetTypeRefProps-Methode](imetadataimport-gettyperefprops-method.md)|Ruft die Metadaten ab, die dem Typ zugeordnet sind, auf den durch das angegebene TypeDef-Token verwiesen wird.|  
|[GetTypeSpecFromToken-Methode](imetadataimport-gettypespecfromtoken-method.md)|Ruft die binäre Metadatensignatur der Typspezifikation ab, die durch das angegebene Token dargestellt wird.|  
|[GetUserString-Methode](imetadataimport-getuserstring-method.md)|Ruft das Zeichenfolgenliteral ab, das durch das angegebene Metadatentoken dargestellt wird.|  
|[IsGlobal-Methode](imetadataimport-isglobal-method.md)|Ruft einen Wert ab, der angibt, ob für das durch das angegebene Metadatentoken dargestellte Feld, die Methode oder den Typ der globale Bereich gilt.|  
|[IsValidToken-Methode](imetadataimport-isvalidtoken-method.md)|Ruft einen Wert ab, der angibt, ob das angegebene Token einen gültigen Verweis auf ein Codeobjekt enthält.|  
|[ResetEnum-Methode](imetadataimport-resetenum-method.md)|Setzt den angegebenen Enumerator auf die der angegebene Position zurück.|  
|[ResolveTypeRef-Methode](imetadataimport-resolvetyperef-method.md)|Ruft Typinformationen für den Typ ab, auf den durch das angegebene TypeRef-Token verwiesen wird.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das Design der `IMetaDataImport`-Schnittstelle soll primär von Tools und Diensten verwendet werden, die Typinformationen importieren (z. B. Entwicklungstools) oder Bereitstellungskomponenten (z. B. Auflösungs-/Aktivierungsdienste) verwalten. Die Methoden in `IMetaDataImport` können in die folgenden Aufgabenkategorien eingeteilt werden:  
  
- Auzählen von Elementauflistungen im Metadatenbereich.  
  
- Suchen nach einem Element, das über eine bestimmte Sammlung von Merkmalen verfügt.  
  
- Abrufen von Eigenschaften eines angegebenen Elements.  
  
- Die Get-Methoden wurden speziell dafür entwickelt, um einwertige Eigenschaften eines Metadatenelements zurückzugeben. Wenn die Eigenschaft ein Verweis auf ein anderes Element ist, wird ein Token für dieses Element zurückgegeben. Jeder Zeigereingabetyp kann NULL sein, um anzugeben, dass der betreffende Wert nicht angefordert wird. Verwenden Sie zum Abrufen von Eigenschaften, die im Wesentlichen Auflistungsobjekte sind (z. B. die Auflistung der Schnittstellen, die eine Klasse implementiert) die Enumerationsmethoden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Metadatenschnittstellen](metadata-interfaces.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
