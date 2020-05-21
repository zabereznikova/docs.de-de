---
title: ICLRStrongName2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
ms.openlocfilehash: 9715369f4cf1b2a7078be14a2fc597f735ab6fd3
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763162"
---
# <a name="iclrstrongname2-interface"></a>ICLRStrongName2-Schnittstelle
Bietet die Möglichkeit, starke Namen mithilfe der SHA-2-Gruppe von sicheren Hash Algorithmen (SHA-256, SHA-384 und SHA-512) zu erstellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[StrongNameGetPublicKeyEx-Methode](strongnamegetpublickeyex-method.md)|Ruft den öffentlichen Schlüssel aus einem Paar aus öffentlichem und privatem Schlüssel ab und gibt einen Hash Algorithmus und einen Signatur Algorithmus an.|  
|[StrongNameSignatureVerificationEx2-Method](strongnamesignatureverificationex2-method.md)|Überprüft die Signatur einer Assembly mit starkem Namen und stellt eine Zuordnung zwischen dem ECMA-Schlüssel und einem echten Schlüssel bereit.|  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
