---
title: Authenticode (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408219307015d5c39cb581b3884ed9810f4c0566
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216345"
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode (Referenz zur nicht verwalteten API)
Unterstützt das Authenticode XrML-Lizenterstellungs- und Überprüfungsmodul.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [_AxlGetIssuerPublicKeyHash-Funktion](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 Ruft den SHA-1-Hash des öffentlichen Schlüssels ab, der dem privaten Schlüssel zugeordnet wurde, der beim Signieren des festgelegten Zertifikats zur Verwendung kam.  
  
 [_AxlPublicKeyBlobToPublicKeyToken-Funktion](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 Berechnet das öffentliche Schlüsseltoken für einen starken Namen aus einem CSP PUBLICKEYBLOB-Format.  
  
 [_AxlRSAKeyValueToPublicKeyToken-Funktion](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 Konvertiert einen Modulo und Exponenten in einen starken Namen des öffentlichen Schlüsseltokens.  
  
 [CertFreeAuthenticodeSignerInfo-Funktion](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 Macht Ressourcen frei, die der AXL_AUTHENTICODE_SIGNER_INFO-Struktur zugewiesen sind.  
  
 [CertFreeAuthenticodeTimestamperInfo-Funktion](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 Macht Ressourcen frei, die der AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur zugewiesen sind.  
  
 [CertTimestampAuthenticodeLicense-Funktion](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 Fügt einer von CertCreateAuthenticodeLicense erstellten Authenticode XrML-Lizenz einen Zeitstempel hinzu.  
  
 [CertVerifyAuthenticodeLicense-Funktion](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 Überprüft die Gültigkeit einer Authenticode-XrML-Lizenz.  
  
 [AXL_AUTHENTICODE_SIGNER_INFO-Struktur](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 Definiert die Authenticode-Informationen des Signaturgebers.  
  
 [AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 Definiert die Authenticode-Informationen des Zeitstempelgebers.  
  
## <a name="see-also"></a>Siehe auch

- [Referenz zur nicht verwalteten API](../../../../docs/framework/unmanaged-api/index.md)
