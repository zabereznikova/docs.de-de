---
title: Sicherheitsfunktionen mit benutzerdefinierten Bindungen
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 1b12907481ccb3f3c5f4b8aaba6ede8ebfa6228a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288306"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="93290-102">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="93290-102">Security Capabilities with Custom Bindings</span></span>

<span data-ttu-id="93290-103">Sie können die meisten der allgemeinen Sicherheitsaufgaben mithilfe einer vom System bereitgestellten Bindung ausführen.</span><span class="sxs-lookup"><span data-stu-id="93290-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="93290-104">Wenn Sie die Sicherheit jedoch detaillierter steuern müssen, können Sie mit <xref:System.ServiceModel.Channels.SecurityBindingElement> eine benutzerdefinierte Bindung erstellen, wie in diesen Themen erläutert.</span><span class="sxs-lookup"><span data-stu-id="93290-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="93290-105">Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [benutzerdefinierte Bindungen](../extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="93290-105">For more information about custom bindings, see [Custom Bindings](../extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93290-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="93290-106">In This Section</span></span>  

 [<span data-ttu-id="93290-107">SecurityBindingElement-Authentifizierungsmodi</span><span class="sxs-lookup"><span data-stu-id="93290-107">SecurityBindingElement Authentication Modes</span></span>](securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="93290-108">Beschreibt die Authentifizierungsmodi, die mit einer benutzerdefinierten Bindung möglich sind.</span><span class="sxs-lookup"><span data-stu-id="93290-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="93290-109">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="93290-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="93290-110">Beschreibt die grundlegenden Schritte zum Erstellen einer benutzerdefinierten Bindung mit einem Sicherheitselement.</span><span class="sxs-lookup"><span data-stu-id="93290-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="93290-111">Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="93290-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="93290-112">Beschreibt das Erstellen eines Sicherheitselements für einen angegebenen Authentifizierungsmodus.</span><span class="sxs-lookup"><span data-stu-id="93290-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="93290-113">Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="93290-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="93290-114">Beschreibt das Deaktivieren von Sicherheitssitzungen beim Erstellen eines Verbunddienstes.</span><span class="sxs-lookup"><span data-stu-id="93290-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="93290-115">Vorgehensweise: Aktivieren der Nachrichtenreplay-Erkennung</span><span class="sxs-lookup"><span data-stu-id="93290-115">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="93290-116">Beschreibt, wie ein Replay-Angriff entdeckt werden kann.</span><span class="sxs-lookup"><span data-stu-id="93290-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="93290-117">Vorgehensweise: Erstellen unterstützender Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="93290-117">How to: Create a Supporting Credential</span></span>](how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="93290-118">Beschreibt das Bereitstellen unterstützender Anmeldeinformationen für einen Dienst, wenn sie vom Dienst benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="93290-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="93290-119">Vorgehensweise: Einrichten einer Signaturbestätigung</span><span class="sxs-lookup"><span data-stu-id="93290-119">How to: Set Up a Signature Confirmation</span></span>](how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="93290-120">Beschreibt die Schritte zum Bestätigen von Signaturen beim digitalen Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="93290-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="93290-121">Vorgehensweise: Festlegen der maximalen Zeitdehnung (Uhrabweichung)</span><span class="sxs-lookup"><span data-stu-id="93290-121">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="93290-122">Beschreibt das Festlegen des maximal zulässigen Zeitunterschieds zwischen einem Dienst und einem Client.</span><span class="sxs-lookup"><span data-stu-id="93290-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="93290-123">Vorgehensweise: Deaktivieren der Verschlüsselung digitaler Signaturen</span><span class="sxs-lookup"><span data-stu-id="93290-123">How to: Disable Encryption of Digital Signatures</span></span>](how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="93290-124">Beschreibt, inwiefern das Deaktivieren der Verschlüsselung von digitalen Signaturen die Leistung verbessern kann.</span><span class="sxs-lookup"><span data-stu-id="93290-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="93290-125">Referenz</span><span class="sxs-lookup"><span data-stu-id="93290-125">Reference</span></span>  

 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="93290-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="93290-126">Related Sections</span></span>  

 [<span data-ttu-id="93290-127">Grundlagen der Schutzebene</span><span class="sxs-lookup"><span data-stu-id="93290-127">Understanding Protection Level</span></span>](../understanding-protection-level.md)  
  
 [<span data-ttu-id="93290-128">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="93290-128">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="93290-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93290-129">See also</span></span>

- [<span data-ttu-id="93290-130">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="93290-130">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="93290-131">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="93290-131">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="93290-132">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="93290-132">System-Provided Bindings</span></span>](../system-provided-bindings.md)
