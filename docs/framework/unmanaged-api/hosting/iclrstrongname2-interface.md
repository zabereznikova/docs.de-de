---
title: ICLRStrongName2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName2
helpviewer_keywords: ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4e1274f675ae9289faa6c530d34cd61d033aa07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongname2-interface"></a>ICLRStrongName2-Schnittstelle
Bietet die Möglichkeit zum Erstellen von starken Namen unter Verwendung der SHA-2-Gruppe des Secure Hash-Algorithmus (SHA-256, SHA-384 und SHA-512).  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[StrongNameGetPublicKeyEx-Methode](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|Ruft den öffentlichen Schlüssel aus einem öffentlichen/privaten Schlüsselpaar und gibt einen Hashalgorithmus und eines Signaturalgorithmus.|  
|[StrongNameSignatureVerificationEx2-Method](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|Überprüft die Signatur einer Assembly mit starkem Namen, und stellt eine Zuordnung aus dem ECMA-Schlüssel, um eine tatsächliche Taste bereit.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
