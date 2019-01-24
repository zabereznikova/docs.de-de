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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8c95249ec28b9018db42ec70443b30ae4f1409c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567216"
---
# <a name="imetadataimport2-interface"></a>IMetaDataImport2-Schnittstelle
Erweitert die [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle, um die Funktion für die Arbeit mit generischen Typen bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumGenericParamConstraints-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|Ruft einen Enumerator für ein Array von generischen Parameter-Einschränkungen, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.|  
|[EnumGenericParams-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|Ruft einen Enumerator für ein Array von generischen Parameter-Token mit dem angegebenen TypeDef oder MethodDef verknüpften token.|  
|[EnumMethodSpecs-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|Ruft einen Enumerator für ein Array von MethodSpec-Token mit dem angegebenen MethodDef oder MemberRef verknüpften token.|  
|[GetGenericParamConstraintProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|Ruft die Einschränkung des generischen Parameters, durch das Token der angegebenen Einschränkung dargestellt zugeordneten Metadaten ab.|  
|[GetGenericParamProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|Ruft die Metadaten, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.|  
|[GetMethodSpecProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|Ruft die Metadatensignatur der Methode verwiesen wird, vom angegebenen MethodSpec token ab.|  
|[GetPEKind-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|Ruft einen Wert, der das Bestimmen der Art des Codes in eine portierbare ausführbare Datei (PE) Datei, in der Regel eine DLL oder EXE-Datei, im aktuellen Metadatenbereich definiert|  
|[GetVersionString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|Ruft die Version der Laufzeit, die verwendet wurde, zur Erstellung der Assembly ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Reflection.PortableExecutableKinds>
- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
