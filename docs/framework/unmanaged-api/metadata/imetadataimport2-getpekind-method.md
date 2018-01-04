---
title: IMetaDataImport2::GetPEKind-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetPEKind
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8dc31877ba3550fa8faf610b831dfd2e7b313ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getpekind-method"></a>IMetaDataImport2::GetPEKind-Methode
Ruft einen Wert, der die Art des Codes in der portierbaren ausführbaren Datei (PE) kennzeichnen Datei, in der Regel eine DLL oder EXE-Datei, die im aktuellen Metadatenbereich definiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pdwPEKind`  
 [out] Ein Zeiger auf den Wert der [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) Enumeration, die die PE-Datei beschreibt.  
  
 `pdwMachine`  
 [out] Ein Zeiger auf einen Wert ab, die Architektur des Computers identifiziert. Finden Sie im nächsten Abschnitt Mögliche Werte.  
  
## <a name="remarks"></a>Hinweise  
 Der referenzierte Wert der `pdwMachine` Parameter kann einen der folgenden sein.  
  
|Wert|Architektur des Computers|  
|-----------|--------------------------|  
|IMAGE_FILE_MACHINE_I386<br /><br /> 0x014C|x86|  
|IMAGE_FILE_MACHINE_IA64<br /><br /> 0 x 0200|Intel IPF|  
|IMAGE_FILE_MACHINE_AMD64<br /><br /> 0x8664|x64|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [CorPEKind-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
