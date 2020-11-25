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
ms.openlocfilehash: d335beecc12e0c1c895e42888ad7172f78062ff7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702536"
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
 vorgenommen Ein Zeiger auf einen Wert der [corpeer Kind](corpekind-enumeration.md) -Enumeration, der die PE-Datei beschreibt.  
  
 `pdwMachine`  
 vorgenommen Ein Zeiger auf einen Wert, der die Architektur des Computers identifiziert. Mögliche Werte finden Sie im nächsten Abschnitt.  
  
## <a name="remarks"></a>Hinweise  

 Der Wert, auf den der-Parameter verweist, `pdwMachine` kann eines der folgenden sein.  
  
|Wert|Computerarchitektur|  
|-----------|--------------------------|  
|IMAGE_FILE_MACHINE_I386<br /><br /> 0x014c|x86|  
|IMAGE_FILE_MACHINE_IA64<br /><br /> 0x0200|Intel IPF|  
|IMAGE_FILE_MACHINE_AMD64<br /><br /> 0x8664|x64|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [CorPEKind-Enumeration](corpekind-enumeration.md)
