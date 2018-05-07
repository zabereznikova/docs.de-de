---
title: Authenticode (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78149d1f8fdad3c11fe693221888f115af84ada2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode (Referenz zur nicht verwalteten API)
Unterstützt das Authenticode XrML-Lizenterstellungs- und Überprüfungsmodul.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [_AxlGetIssuerPublicKeyHash-Funktion](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 Ruft den SHA-1-Hash des öffentlichen Schlüssels ab, der dem privaten Schlüssel zugeordnet wurde, der beim Signieren des festgelegten Zertifikats zur Verwendung kam.  
  
 [_AxlPublicKeyBlobToPublicKeyToken-Funktion](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 Berechnet den starken Namen des öffentlichen Schlüsseltokens aus einem CSP PUBLICKEYBLOB-Format.  
  
 [_AxlRSAKeyValueToPublicKeyToken-Funktion](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 Konvertiert ein Modulo und einen Exponenten in ein Token für den öffentlichen Schlüssel für einen starken Namen.  
  
 [CertFreeAuthenticodeSignerInfo-Funktion](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 Macht Ressourcen frei, die der AXL_AUTHENTICODE_SIGNER_INFO-Struktur zugewiesen sind.  
  
 [CertFreeAuthenticodeTimestamperInfo-Funktion](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 Macht Ressourcen frei, die der AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur zugewiesen sind.  
  
 [CertTimestampAuthenticodeLicense-Funktion](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 Fügt einer von CertCreateAuthenticodeLicense erstellten Authenticode XrML-Lizenz einen Zeitstempel hinzu.  
  
 [CertVerifyAuthenticodeLicense-Funktion](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 Überprüft die Gültigkeit einer Authenticode-XrML-Lizenz.  
  
 [AXL_AUTHENTICODE_SIGNER_INFO-Struktur](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 Definiert Informationen zum Signaturgeber für Authenticode.  
  
 [AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 Definiert Informationen zum Ersteller des Zeitstempels für Authenticode.  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur nicht verwalteten API](../../../../docs/framework/unmanaged-api/index.md)
