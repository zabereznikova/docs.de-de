---
title: Sicherheitsfunktionen mit benutzerdefinierten Bindungen
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 25d203fa706eeb0d0ccf1eaf4367ffa5bd7b83aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990924"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="76972-102">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="76972-102">Security Capabilities with Custom Bindings</span></span>
<span data-ttu-id="76972-103">Sie können die meisten der allgemeinen Sicherheitsaufgaben mithilfe einer vom System bereitgestellten Bindung ausführen.</span><span class="sxs-lookup"><span data-stu-id="76972-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="76972-104">Wenn Sie die Sicherheit jedoch detaillierter steuern müssen, können Sie mit <xref:System.ServiceModel.Channels.SecurityBindingElement> eine benutzerdefinierte Bindung erstellen, wie in diesen Themen erläutert.</span><span class="sxs-lookup"><span data-stu-id="76972-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="76972-105">Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="76972-105">For more information about custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76972-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="76972-106">In This Section</span></span>  
 [<span data-ttu-id="76972-107">SecurityBindingElement-Authentifizierungsmodi</span><span class="sxs-lookup"><span data-stu-id="76972-107">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="76972-108">Beschreibt die Authentifizierungsmodi, die mit einer benutzerdefinierten Bindung möglich sind.</span><span class="sxs-lookup"><span data-stu-id="76972-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="76972-109">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="76972-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="76972-110">Beschreibt die grundlegenden Schritte zum Erstellen einer benutzerdefinierten Bindung mit einem Sicherheitselement.</span><span class="sxs-lookup"><span data-stu-id="76972-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="76972-111">Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="76972-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="76972-112">Beschreibt das Erstellen eines Sicherheitselements für einen angegebenen Authentifizierungsmodus.</span><span class="sxs-lookup"><span data-stu-id="76972-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="76972-113">Vorgehensweise: Deaktivieren von Sicherheitssitzungen auf einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="76972-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="76972-114">Beschreibt das Deaktivieren von Sicherheitssitzungen beim Erstellen eines Verbunddienstes.</span><span class="sxs-lookup"><span data-stu-id="76972-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="76972-115">Vorgehensweise: Aktivieren der Nachrichtenreplay-Erkennung</span><span class="sxs-lookup"><span data-stu-id="76972-115">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="76972-116">Beschreibt, wie ein Replay-Angriff entdeckt werden kann.</span><span class="sxs-lookup"><span data-stu-id="76972-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="76972-117">Vorgehensweise: Erstellen Sie unterstützenden Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="76972-117">How to: Create a Supporting Credential</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="76972-118">Beschreibt das Bereitstellen unterstützender Anmeldeinformationen für einen Dienst, wenn sie vom Dienst benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="76972-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="76972-119">Vorgehensweise: Einrichten einer Signaturbestätigung</span><span class="sxs-lookup"><span data-stu-id="76972-119">How to: Set Up a Signature Confirmation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="76972-120">Beschreibt die Schritte zum Bestätigen von Signaturen beim digitalen Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="76972-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="76972-121">Vorgehensweise: Festlegen der maximalen Zeitdehnung Uhrabweichung</span><span class="sxs-lookup"><span data-stu-id="76972-121">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="76972-122">Beschreibt das Festlegen des maximal zulässigen Zeitunterschieds zwischen einem Dienst und einem Client.</span><span class="sxs-lookup"><span data-stu-id="76972-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="76972-123">Vorgehensweise: Deaktivieren der Verschlüsselung digitaler Signaturen</span><span class="sxs-lookup"><span data-stu-id="76972-123">How to: Disable Encryption of Digital Signatures</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="76972-124">Beschreibt, inwiefern das Deaktivieren der Verschlüsselung von digitalen Signaturen die Leistung verbessern kann.</span><span class="sxs-lookup"><span data-stu-id="76972-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="76972-125">Referenz</span><span class="sxs-lookup"><span data-stu-id="76972-125">Reference</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [<span data-ttu-id="76972-126">\<security></span><span class="sxs-lookup"><span data-stu-id="76972-126">\<security></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="76972-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="76972-127">Related Sections</span></span>  
 [<span data-ttu-id="76972-128">Grundlagen der Schutzebene</span><span class="sxs-lookup"><span data-stu-id="76972-128">Understanding Protection Level</span></span>](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [<span data-ttu-id="76972-129">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="76972-129">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="76972-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76972-130">See also</span></span>

- [<span data-ttu-id="76972-131">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="76972-131">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
- [<span data-ttu-id="76972-132">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="76972-132">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="76972-133">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="76972-133">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
