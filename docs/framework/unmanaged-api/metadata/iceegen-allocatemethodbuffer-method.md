---
title: ICeeGen::AllocateMethodBuffer-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7be1bd2934fbb2e09a39c3042fa9ae314e89d629
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083763"
---
# <a name="iceegenallocatemethodbuffer-method"></a>ICeeGen::AllocateMethodBuffer-Methode
Erstellt einen Puffer mit der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode.  
  
 Diese Methode ist veraltet und sollte nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cchBuffer`  
 [in] Die Länge des zu erstellenden Puffers.  
  
 `lpBuffer`  
 [out] Der zurückgegebene Puffer.  
  
 `RVA`  
 [out] Die relative virtuelle Adresse der Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICeeGen-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
