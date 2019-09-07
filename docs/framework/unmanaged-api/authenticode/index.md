---
title: Authenticode (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2c0163d03a19a7bc00ae705fd633ef4f0880082
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776555"
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode (Referenz zur nicht verwalteten API)
Unterstützt das Authenticode XrML-Lizenterstellungs- und Überprüfungsmodul.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [_AxlGetIssuerPublicKeyHash-Funktion](axlgetissuerpublickeyhash-function.md)  
 Ruft den SHA-1-Hash des öffentlichen Schlüssels ab, der dem privaten Schlüssel zugeordnet wurde, der beim Signieren des festgelegten Zertifikats zur Verwendung kam.  
  
 [_AxlPublicKeyBlobToPublicKeyToken-Funktion](axlpublickeyblobtopublickeytoken-function.md)  
 Berechnet das öffentliche Schlüsseltoken für einen starken Namen aus einem CSP PUBLICKEYBLOB-Format.  
  
 [_AxlRSAKeyValueToPublicKeyToken-Funktion](axlrsakeyvaluetopublickeytoken-function.md)  
 Konvertiert einen Modulo und Exponenten in einen starken Namen des öffentlichen Schlüsseltokens.  
  
 [CertFreeAuthenticodeSignerInfo-Funktion](certfreeauthenticodesignerinfo-function.md)  
 Macht Ressourcen frei, die der AXL_AUTHENTICODE_SIGNER_INFO-Struktur zugewiesen sind.  
  
 [CertFreeAuthenticodeTimestamperInfo-Funktion](certfreeauthenticodetimestamperinfo-function.md)  
 Macht Ressourcen frei, die der AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur zugewiesen sind.  
  
 [CertTimestampAuthenticodeLicense-Funktion](certtimestampauthenticodelicense-function.md)  
 Fügt einer von CertCreateAuthenticodeLicense erstellten Authenticode XrML-Lizenz einen Zeitstempel hinzu.  
  
 [CertVerifyAuthenticodeLicense-Funktion](certverifyauthenticodelicense-function.md)  
 Überprüft die Gültigkeit einer Authenticode-XrML-Lizenz.  
  
 [AXL_AUTHENTICODE_SIGNER_INFO-Struktur](axl-authenticode-signer-info-structure.md)  
 Definiert die Authenticode-Informationen des Signaturgebers.  
  
 [AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur](axl-authenticode-timestamper-info-structure.md)  
 Definiert die Authenticode-Informationen des Zeitstempelgebers.  
  
## <a name="see-also"></a>Siehe auch

- [Referenz zur nicht verwalteten API](../index.md)
