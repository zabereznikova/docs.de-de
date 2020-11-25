---
title: Authenticode (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 9b3e1585278bda82dedf7542e866a551867b9c9f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674046"
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
  
## <a name="see-also"></a>Weitere Informationen

- [Referenz zur nicht verwalteten API](../index.md)
