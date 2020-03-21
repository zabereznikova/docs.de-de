---
title: ICeeGen::GetSectionBlock-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: a494b1aaa762549528e92ab93d18929ef73eb8da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176083"
---
# <a name="iceegengetsectionblock-method"></a>ICeeGen::GetSectionBlock-Methode
Ruft einen Abschnittsblock der Codebasis ab.  
  
 Diese Methode ist veraltet und sollte nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a>Parameter  
 `section`  
 [in] Der Abschnitt, aus dem ein Block der Codebasis abgerufen werden soll.  
  
 `len`  
 [in] Die Länge des abrufbaren Blocks.  
  
 `align`  
 [in] Das Byte relativ zum Anfang des Abschnitts, mit dem das erste Byte des Blocks ausgerichtet werden soll. Dies ist die Position des Blocks innerhalb des Abschnitts.  
  
 `ppBytes`  
 [out] Ein Zeiger auf eine Position, die die Adresse des abgerufenen Blocks empfängt.  
  
## <a name="remarks"></a>Bemerkungen  
 Rufen `GetSectionBlock` Sie nur an, wenn Sie spezielle Abschnittsanforderungen haben, die nicht von anderen Methoden verarbeitet werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICeeGen-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
