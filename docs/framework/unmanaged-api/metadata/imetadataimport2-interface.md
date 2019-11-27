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
ms.openlocfilehash: 0fd7915ef46899bdce8312bc6e8a466167e26382
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429208"
---
# <a name="imetadataimport2-interface"></a>IMetaDataImport2-Schnittstelle
Erweitert die [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Schnittstelle, um die Funktion zum Arbeiten mit generischen Typen bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumGenericParamConstraints-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|Ruft einen Enumerator für ein Array von generischen Parameter Einschränkungen ab, die dem generischen Parameter zugeordnet sind, der durch das angegebene Token dargestellt wird.|  
|[EnumGenericParams-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|Ruft einen Enumerator für ein Array von generischen Parameter Token ab, die dem angegebenen TypeDef-oder MethodDef-Token zugeordnet sind.|  
|[EnumMethodSpecs-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|Ruft einen Enumerator für ein Array von MethodSpec-Token ab, das mit dem angegebenen MethodDef-oder mitgliedsverweistoken verknüpft ist.|  
|[GetGenericParamConstraintProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|Ruft die Metadaten ab, die der durch das angegebene Einschränkungs Token dargestellten generischen Parameter Einschränkung zugeordnet sind.|  
|[GetGenericParamProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|Ruft die Metadaten ab, die dem durch das angegebene Token dargestellten generischen Parameter zugeordnet sind.|  
|[GetMethodSpecProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|Ruft die Metadatensignatur der Methode ab, auf die durch das angegebene MethodSpec-Token verwiesen wird.|  
|[GetPEKind-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|Ruft einen Wert ab, der die Art des Codes in einer portablen ausführbaren Datei (PE) identifiziert, normalerweise eine DLL-oder exe-Datei, die im aktuellen Metadatenbereich definiert ist.|  
|[GetVersionString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|Ruft die Versionsnummer der Laufzeit ab, die zum Erstellen der Assembly verwendet wurde.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.PortableExecutableKinds>
- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
