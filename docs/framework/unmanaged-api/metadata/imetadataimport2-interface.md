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
ms.openlocfilehash: fe9e87618291218a41e52f80198ce9068c9c56e2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490393"
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
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- <xref:System.Reflection.PortableExecutableKinds>
- [Metadatenschnittstellen](metadata-interfaces.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
