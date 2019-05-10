---
title: 'Vorgehensweise: Einheitliche Verweise auf X.509-Zertifikate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: 2214517784d311cbd0fe487fd6db2cbf48189955
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662782"
---
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="488b9-102">Vorgehensweise: Einheitliche Verweise auf X.509-Zertifikate</span><span class="sxs-lookup"><span data-stu-id="488b9-102">How to: Consistently Reference X.509 Certificates</span></span>
<span data-ttu-id="488b9-103">Sie haben verschiedene Möglichkeiten, Zertifikate anzugeben: anhand des Hashwerts des Zertifikats, anhand des Ausstellers und der Seriennummer oder anhand der Schlüsselkennung des Antragstellers (Subject Key Identifier, SKI).</span><span class="sxs-lookup"><span data-stu-id="488b9-103">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="488b9-104">Die Schlüsselkennung des Antragstellers gibt den öffentlichen Schlüssel des Zertifikatantagstellers eindeutig an. Sie wird häufig für digitale XML-Signaturen verwendet.</span><span class="sxs-lookup"><span data-stu-id="488b9-104">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="488b9-105">Der SKI-Wert wird in der Regel Teil des x. 509-Zertifikats als ein *x. 509-zertifikaterweiterung*.</span><span class="sxs-lookup"><span data-stu-id="488b9-105">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> <span data-ttu-id="488b9-106">Windows Communication Foundation (WCF) hat den Standardwert *verweisstil* , den Aussteller und die Seriennummer verwendet, wenn die SKI-Erweiterung aus dem Zertifikat nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="488b9-106">Windows Communication Foundation (WCF) has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="488b9-107">Enthält das Zertifikat die SKI-Erweiterung, verwendet der Standardverweis die Schlüsselkennung des Antragstellers, um auf das Zertifikat zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="488b9-107">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="488b9-108">Wenn zwischendurch durch die Entwicklung einer Anwendung, wird Sie von der Verwendung von Zertifikaten, die nicht die SKI-Erweiterung für Zertifikate verwenden, die die SKI-Erweiterung verwenden wechseln, ändert sich auch der verweisstil in generierten WCF Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="488b9-108">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in WCF-generated messages also changes.</span></span>  
  
 <span data-ttu-id="488b9-109">Wenn unabhängig vom Vorhandensein einer SKI-Erweiterung ein einheitlicher Verweisstil erforderlich ist, kann der gewünschte Verweisstil wie im folgenden Code dargestellt konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="488b9-109">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="488b9-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="488b9-110">Example</span></span>  
 <span data-ttu-id="488b9-111">Im folgenden Beispiel wird ein benutzerdefiniertes Sicherheitsbindungselement erstellt, das einen einzigen einheitlichen Verweisstil, den Namen des Ausstellers und die Seriennummer verwendet.</span><span class="sxs-lookup"><span data-stu-id="488b9-111">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="488b9-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="488b9-112">Compiling the Code</span></span>  
 <span data-ttu-id="488b9-113">Die folgenden Namespaces sind zum Kompilieren des Codes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="488b9-113">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="488b9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="488b9-114">See also</span></span>

- [<span data-ttu-id="488b9-115">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="488b9-115">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
