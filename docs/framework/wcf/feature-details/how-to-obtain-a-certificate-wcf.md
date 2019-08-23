---
title: 'Vorgehensweise: Abrufen eines Zertifikats (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: e720a6742506f6270fda65de12f510c2a6224873
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929192"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="282b0-102">Vorgehensweise: Abrufen eines Zertifikats (WCF)</span><span class="sxs-lookup"><span data-stu-id="282b0-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="282b0-103">Um eine der Windows Communication Foundation (WCF)-Funktionen von verwenden zu können, die X. 509-Zertifikate verwenden, erhalten Sie zuerst Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="282b0-103">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="282b0-104">So rufen Sie ein X.509-Zertifikat ab</span><span class="sxs-lookup"><span data-stu-id="282b0-104">To obtain an X.509 certificate</span></span>  
  
1. <span data-ttu-id="282b0-105">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="282b0-105">Choose one of the following:</span></span>  
  
    - <span data-ttu-id="282b0-106">Erwerben Sie ein Zertifikat von einer Zertifizierungsstelle, z. B. VeriSign, Inc.</span><span class="sxs-lookup"><span data-stu-id="282b0-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    - <span data-ttu-id="282b0-107">Richten Sie einen eigenen Zertifikatdienst ein, und lassen Sie die Zertifikate von einer Zertifizierungsstelle signieren.</span><span class="sxs-lookup"><span data-stu-id="282b0-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]<span data-ttu-id="282b0-108">, Windows&#160;2000 Server, Windows&#160;2000 Server Datacenter und Windows&#160;2000 Datacenter Server verfügen alle über Zertifikatdienste mit Public Key Infrastructure (PKI)-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="282b0-108">, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="282b0-109">Verwenden Sie unter Windows Server 2008 die Rolle " [Active Directory-Zertifikat Dienste](https://go.microsoft.com/fwlink/?LinkID=153483) ", um eine Zertifizierungsstelle zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="282b0-109">In Windows Server 2008, use the [Active Directory Certificate Services](https://go.microsoft.com/fwlink/?LinkID=153483) role to manage a certification authority.</span></span>  
  
    - <span data-ttu-id="282b0-110">Richten Sie einen eigenen Zertifikatsdienst ein, und lassen Sie die Zertifikate nicht signieren.</span><span class="sxs-lookup"><span data-stu-id="282b0-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="282b0-111">Unabhängig vom gewählten Ansatz muss der Empfänger der SOAP-Anforderung, die das X.509-Zertifikat enthält, dem X.509-Zertifikat vertrauen.</span><span class="sxs-lookup"><span data-stu-id="282b0-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="282b0-112">Dies bedeutet, dass sich das X.509-Zertifikat oder ein Aussteller in der Zertifikatkette im Speicher für vertrauenswürdige Personen befindet und sich das X.509-Zertifikat nicht im Speicher für nicht vertrauenswürdige Zertifikate befindet.</span><span class="sxs-lookup"><span data-stu-id="282b0-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="282b0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="282b0-113">See also</span></span>

- [<span data-ttu-id="282b0-114">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="282b0-114">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="282b0-115">Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="282b0-115">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
