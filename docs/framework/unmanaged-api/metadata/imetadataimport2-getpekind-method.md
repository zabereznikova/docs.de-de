---
title: IMetaDataImport2::GetPEKind-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9dda1fb38546138d52b5fe61754d5497e676c37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113481"
---
# <a name="imetadataimport2getpekind-method"></a>IMetaDataImport2::GetPEKind-Methode
Ruft einen Wert, der das Bestimmen der Art des Codes in der portierbaren ausführbaren Datei (PE) Datei, in der Regel eine DLL oder EXE-Datei, die im aktuellen Metadatenbereich definiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pdwPEKind`  
 [out] Ein Zeiger auf den Wert der [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) -Enumeration, die PE-Datei beschreibt.  
  
 `pdwMachine`  
 [out] Ein Zeiger auf einen Wert ab, die Architektur des Computers identifiziert. Finden Sie im nächsten Abschnitt Mögliche Werte.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert, der auf die verwiesen wird durch die `pdwMachine` Parameter kann einen der folgenden sein.  
  
|Wert|Architektur des Computers|  
|-----------|--------------------------|  
|IMAGE_FILE_MACHINE_I386<br /><br /> 0x014C|x86|  
|IMAGE_FILE_MACHINE_IA64<br /><br /> 0x0200|Intel IPF|  
|IMAGE_FILE_MACHINE_AMD64<br /><br /> 0x8664|x64|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [CorPEKind-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
