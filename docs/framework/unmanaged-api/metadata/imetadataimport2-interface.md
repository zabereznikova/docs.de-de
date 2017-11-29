---
title: IMetaDataImport2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2
helpviewer_keywords: IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1b00879f1d22d49e5f0dc3bdb072e0545feda68d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2-interface"></a>IMetaDataImport2-Schnittstelle
Erweitert die [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle, um die Funktion der Arbeit mit generischen Typen bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumGenericParamConstraints-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|Ruft einen Enumerator für ein Array mit Einschränkungen für generische Typparameter durch das angegebene Token dargestellten generischen Parameter zugeordnet.|  
|[EnumGenericParams-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|Ruft einen Enumerator für ein Array von generischen Parameter-Token mit dem angegebenen TypeDef- oder MethodDef verknüpften token.|  
|[EnumMethodSpecs-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|Ruft einen Enumerator für ein Array von MethodSpec-Token mit der angegebenen MethodDef oder MemberRef token.|  
|[GetGenericParamConstraintProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|Ruft die Einschränkung des generischen Parameters, durch die angegebene Einschränkung-Token dargestellt wird zugeordneten Metadaten ab.|  
|[GetGenericParamProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|Ruft die Metadaten, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.|  
|[GetMethodSpecProps-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|Ruft die Metadatensignatur der Methode verwiesen wird, vom angegebenen MethodSpec-token ab.|  
|[GetPEKind-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|Ruft einen Wert, der die Art des Codes in einer portablen ausführbaren Datei (PE) kennzeichnen Datei, in der Regel eine DLL oder EXE-Datei, im aktuellen Metadatenbereich definiert|  
|[GetVersionString-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|Ruft die Version der Laufzeit, die verwendet wurde, zum Erstellen der Assembly ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection.PortableExecutableKinds>  
 [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
