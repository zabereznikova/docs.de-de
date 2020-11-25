---
title: IMetaDataImport2-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: a845ecfde6583d625d2a8f165443344ff9e40d05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702549"
---
# <a name="imetadataimport2-interface"></a>IMetaDataImport2-Schnittstelle

Erweitert die [IMetaDataImport](imetadataimport-interface.md) -Schnittstelle, um die Funktion zum Arbeiten mit generischen Typen bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnumGenericParamConstraints-Methode](imetadataimport2-enumgenericparamconstraints-method.md)|Ruft einen Enumerator für ein Array von generischen Parameter Einschränkungen ab, die dem generischen Parameter zugeordnet sind, der durch das angegebene Token dargestellt wird.|  
|[EnumGenericParams-Methode](imetadataimport2-enumgenericparams-method.md)|Ruft einen Enumerator für ein Array von generischen Parameter Token ab, die dem angegebenen TypeDef-oder MethodDef-Token zugeordnet sind.|  
|[EnumMethodSpecs-Methode](imetadataimport2-enummethodspecs-method.md)|Ruft einen Enumerator für ein Array von MethodSpec-Token ab, das mit dem angegebenen MethodDef-oder mitgliedsverweistoken verknüpft ist.|  
|[GetGenericParamConstraintProps-Methode](imetadataimport2-getgenericparamconstraintprops-method.md)|Ruft die Metadaten ab, die der durch das angegebene Einschränkungs Token dargestellten generischen Parameter Einschränkung zugeordnet sind.|  
|[GetGenericParamProps-Methode](imetadataimport2-getgenericparamprops-method.md)|Ruft die Metadaten ab, die dem durch das angegebene Token dargestellten generischen Parameter zugeordnet sind.|  
|[GetMethodSpecProps-Methode](imetadataimport2-getmethodspecprops-method.md)|Ruft die Metadatensignatur der Methode ab, auf die durch das angegebene MethodSpec-Token verwiesen wird.|  
|[GetPEKind-Methode](imetadataimport2-getpekind-method.md)|Ruft einen Wert ab, der die Art des Codes in einer portablen ausführbaren Datei (PE) identifiziert, normalerweise eine DLL-oder exe-Datei, die im aktuellen Metadatenbereich definiert ist.|  
|[GetVersionString-Methode](imetadataimport2-getversionstring-method.md)|Ruft die Versionsnummer der Laufzeit ab, die zum Erstellen der Assembly verwendet wurde.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Reflection.PortableExecutableKinds>
- [Metadatenschnittstellen](metadata-interfaces.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
