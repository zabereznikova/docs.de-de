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
ms.openlocfilehash: 0464c61e4ff01483e10fb5708d5ed4b5f5ed63d0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445236"
---
# <a name="imetadataimport2getpekind-method"></a>IMetaDataImport2::GetPEKind-Methode
Ruft einen Wert ab, der die Art des Codes in der Datei mit der portablen ausführbaren Datei (PE) identifiziert, in der Regel eine DLL-oder exe-Datei, die im aktuellen Metadatenbereich definiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pdwPEKind`  
 vorgenommen Ein Zeiger auf einen Wert der [corpeer Kind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) -Enumeration, der die PE-Datei beschreibt.  
  
 `pdwMachine`  
 vorgenommen Ein Zeiger auf einen Wert, der die Architektur des Computers identifiziert. Mögliche Werte finden Sie im nächsten Abschnitt.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert, auf den der `pdwMachine`-Parameter verweist, kann einen der folgenden Werte aufweisen.  
  
|Wert|Computerarchitektur|  
|-----------|--------------------------|  
|IMAGE_FILE_MACHINE_I386<br /><br /> 0x014C|x86|  
|IMAGE_FILE_MACHINE_IA64<br /><br /> 0x0200|Intel IPF|  
|IMAGE_FILE_MACHINE_AMD64<br /><br /> 0x8664|x64|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [CorPEKind-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
