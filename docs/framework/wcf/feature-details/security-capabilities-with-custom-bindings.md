---
title: Sicherheitsfunktionen mit benutzerdefinierten Bindungen
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
author: BrucePerlerMS
ms.openlocfilehash: 35d2477af3dc7ce6fdd075055fff9e687bdc2a60
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47196732"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="2ea64-102">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="2ea64-102">Security Capabilities with Custom Bindings</span></span>
<span data-ttu-id="2ea64-103">Sie können die meisten der allgemeinen Sicherheitsaufgaben mithilfe einer vom System bereitgestellten Bindung ausführen.</span><span class="sxs-lookup"><span data-stu-id="2ea64-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="2ea64-104">Wenn Sie die Sicherheit jedoch detaillierter steuern müssen, können Sie mit <xref:System.ServiceModel.Channels.SecurityBindingElement> eine benutzerdefinierte Bindung erstellen, wie in diesen Themen erläutert.</span><span class="sxs-lookup"><span data-stu-id="2ea64-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="2ea64-105">Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="2ea64-105">For more information about custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ea64-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2ea64-106">In This Section</span></span>  
 [<span data-ttu-id="2ea64-107">SecurityBindingElement-Authentifizierungsmodi</span><span class="sxs-lookup"><span data-stu-id="2ea64-107">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="2ea64-108">Beschreibt die Authentifizierungsmodi, die mit einer benutzerdefinierten Bindung möglich sind.</span><span class="sxs-lookup"><span data-stu-id="2ea64-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="2ea64-109">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="2ea64-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="2ea64-110">Beschreibt die grundlegenden Schritte zum Erstellen einer benutzerdefinierten Bindung mit einem Sicherheitselement.</span><span class="sxs-lookup"><span data-stu-id="2ea64-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="2ea64-111">Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="2ea64-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="2ea64-112">Beschreibt das Erstellen eines Sicherheitselements für einen angegebenen Authentifizierungsmodus.</span><span class="sxs-lookup"><span data-stu-id="2ea64-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="2ea64-113">Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="2ea64-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="2ea64-114">Beschreibt das Deaktivieren von Sicherheitssitzungen beim Erstellen eines Verbunddienstes.</span><span class="sxs-lookup"><span data-stu-id="2ea64-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="2ea64-115">Vorgehensweise: Aktivieren der Nachrichtenreplayerkennung</span><span class="sxs-lookup"><span data-stu-id="2ea64-115">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="2ea64-116">Beschreibt, wie ein Replay-Angriff entdeckt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ea64-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="2ea64-117">Vorgehensweise: Erstellen unterstützender Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="2ea64-117">How to: Create a Supporting Credential</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="2ea64-118">Beschreibt das Bereitstellen unterstützender Anmeldeinformationen für einen Dienst, wenn sie vom Dienst benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="2ea64-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="2ea64-119">Vorgehensweise: Einrichten einer Signaturbestätigung</span><span class="sxs-lookup"><span data-stu-id="2ea64-119">How to: Set Up a Signature Confirmation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="2ea64-120">Beschreibt die Schritte zum Bestätigen von Signaturen beim digitalen Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="2ea64-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="2ea64-121">Vorgehensweise: Festlegen der maximalen Zeitdehnung (Uhrabweichung)</span><span class="sxs-lookup"><span data-stu-id="2ea64-121">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="2ea64-122">Beschreibt das Festlegen des maximal zulässigen Zeitunterschieds zwischen einem Dienst und einem Client.</span><span class="sxs-lookup"><span data-stu-id="2ea64-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="2ea64-123">Vorgehensweise: Deaktivieren der Verschlüsselung digitaler Signaturen</span><span class="sxs-lookup"><span data-stu-id="2ea64-123">How to: Disable Encryption of Digital Signatures</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="2ea64-124">Beschreibt, inwiefern das Deaktivieren der Verschlüsselung von digitalen Signaturen die Leistung verbessern kann.</span><span class="sxs-lookup"><span data-stu-id="2ea64-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2ea64-125">Referenz</span><span class="sxs-lookup"><span data-stu-id="2ea64-125">Reference</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [<span data-ttu-id="2ea64-126">\<security></span><span class="sxs-lookup"><span data-stu-id="2ea64-126">\<security></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="2ea64-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="2ea64-127">Related Sections</span></span>  
 [<span data-ttu-id="2ea64-128">Grundlagen der Schutzebene</span><span class="sxs-lookup"><span data-stu-id="2ea64-128">Understanding Protection Level</span></span>](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [<span data-ttu-id="2ea64-129">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="2ea64-129">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ea64-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ea64-130">See Also</span></span>  
 [<span data-ttu-id="2ea64-131">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2ea64-131">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [<span data-ttu-id="2ea64-132">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2ea64-132">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="2ea64-133">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="2ea64-133">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
