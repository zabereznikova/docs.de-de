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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bf9e3d2df8f507e118b393007c3958358a830cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763723"
---
# <a name="iclrstrongname2-interface"></a>ICLRStrongName2-Schnittstelle
Bietet die Möglichkeit zum Erstellen von starken Namen unter Verwendung der SHA-2-Gruppe der Hashalgorithmen (SHA-256, SHA-384 und SHA-512) sichern.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[StrongNameGetPublicKeyEx-Methode](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|Ruft den öffentlichen Schlüssel aus einem öffentlichen/privaten Schlüsselpaar und ein Hash-Algorithmus und eines Signaturalgorithmus angibt.|  
|[StrongNameSignatureVerificationEx2-Method](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|Überprüft die Signatur einer Assembly mit starkem Namen, und stellt eine Zuordnung zwischen den ECMA-Schlüssel zu einem echten Schlüssel.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
