---
title: Authenticode (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 1b8b2222950c75f7f9d2ec2704f722087645cd7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73132457"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="3c13f-102">Authenticode (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="3c13f-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="3c13f-103">Unterstützt das Authenticode XrML-Lizenterstellungs- und Überprüfungsmodul.</span><span class="sxs-lookup"><span data-stu-id="3c13f-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c13f-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3c13f-104">In This Section</span></span>  
 [<span data-ttu-id="3c13f-105">_AxlGetIssuerPublicKeyHash-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c13f-105">_AxlGetIssuerPublicKeyHash Function</span></span>](axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="3c13f-106">Ruft den SHA-1-Hash des öffentlichen Schlüssels ab, der dem privaten Schlüssel zugeordnet wurde, der beim Signieren des festgelegten Zertifikats zur Verwendung kam.</span><span class="sxs-lookup"><span data-stu-id="3c13f-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="3c13f-107">_AxlPublicKeyBlobToPublicKeyToken-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c13f-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="3c13f-108">Berechnet das öffentliche Schlüsseltoken für einen starken Namen aus einem CSP PUBLICKEYBLOB-Format.</span><span class="sxs-lookup"><span data-stu-id="3c13f-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="3c13f-109">_AxlRSAKeyValueToPublicKeyToken-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c13f-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="3c13f-110">Konvertiert einen Modulo und Exponenten in einen starken Namen des öffentlichen Schlüsseltokens.</span><span class="sxs-lookup"><span data-stu-id="3c13f-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="3c13f-111">CertFreeAuthenticodeSignerInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c13f-111">CertFreeAuthenticodeSignerInfo Function</span></span>](certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="3c13f-112">Macht Ressourcen frei, die der AXL_AUTHENTICODE_SIGNER_INFO-Struktur zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="3c13f-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="3c13f-113">CertFreeAuthenticodeTimestamperInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c13f-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="3c13f-114">Macht Ressourcen frei, die der AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="3c13f-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="3c13f-115">CertTimestampAuthenticodeLicense-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c13f-115">CertTimestampAuthenticodeLicense Function</span></span>](certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="3c13f-116">Fügt einer von CertCreateAuthenticodeLicense erstellten Authenticode XrML-Lizenz einen Zeitstempel hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c13f-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="3c13f-117">CertVerifyAuthenticodeLicense-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c13f-117">CertVerifyAuthenticodeLicense Function</span></span>](certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="3c13f-118">Überprüft die Gültigkeit einer Authenticode-XrML-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="3c13f-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="3c13f-119">AXL_AUTHENTICODE_SIGNER_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="3c13f-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="3c13f-120">Definiert die Authenticode-Informationen des Signaturgebers.</span><span class="sxs-lookup"><span data-stu-id="3c13f-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="3c13f-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="3c13f-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="3c13f-122">Definiert die Authenticode-Informationen des Zeitstempelgebers.</span><span class="sxs-lookup"><span data-stu-id="3c13f-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c13f-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c13f-123">See also</span></span>

- [<span data-ttu-id="3c13f-124">Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="3c13f-124">Unmanaged API Reference</span></span>](../index.md)
