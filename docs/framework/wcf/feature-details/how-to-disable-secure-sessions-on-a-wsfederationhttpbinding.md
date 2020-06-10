---
title: 'Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
ms.openlocfilehash: df057d64feb89d1e43b938b36cb48f2f103b17d0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595387"
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a><span data-ttu-id="44694-102">Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="44694-102">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>

<span data-ttu-id="44694-103">Für einige Dienste sind möglicherweise verbundene Anmeldeinformationen notwendig, sichere Sitzungen werden jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="44694-103">Some services may require federated credentials but not support secure sessions.</span></span> <span data-ttu-id="44694-104">In diesem Fall müssen Sie die Funktion für sichere Sitzungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="44694-104">In that case, you must disable the secure session feature.</span></span> <span data-ttu-id="44694-105">Im Gegensatz zu <xref:System.ServiceModel.WSHttpBinding> bietet die <xref:System.ServiceModel.WSFederationHttpBinding>-Klasse keinen Weg, um sichere Sitzungen bei der Kommunikation mit einem Dienst zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="44694-105">Unlike the <xref:System.ServiceModel.WSHttpBinding>, the <xref:System.ServiceModel.WSFederationHttpBinding> class does not provide a way to disable secure sessions when communicating with a service.</span></span> <span data-ttu-id="44694-106">Sie müssen vielmehr eine benutzerdefinierte Bindung erstellen, die die Einstellungen der sicheren Sitzung durch einen Bootstrap ersetzen.</span><span class="sxs-lookup"><span data-stu-id="44694-106">Instead, you must create a custom binding that replaces the secure session settings with a bootstrap.</span></span>

<span data-ttu-id="44694-107">In diesem Thema wird veranschaulicht, wie Sie das Bindungselement, das sich in einer <xref:System.ServiceModel.WSFederationHttpBinding> befindet, ändern können, um eine benutzerdefinierte Bindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="44694-107">This topic demonstrates how to modify the binding elements contained within a <xref:System.ServiceModel.WSFederationHttpBinding> to create a custom binding.</span></span> <span data-ttu-id="44694-108">Das Ergebnis entspricht <xref:System.ServiceModel.WSFederationHttpBinding> mit Ausnahme der Tatsache, dass keine sicheren Sitzungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44694-108">The result is identical to the <xref:System.ServiceModel.WSFederationHttpBinding> except that it does not use secure sessions.</span></span>

## <a name="to-create-a-custom-federated-binding-without-secure-session"></a><span data-ttu-id="44694-109">So erstellen Sie eine benutzerdefinierte Verbundbindung ohne sichere Sitzung</span><span class="sxs-lookup"><span data-stu-id="44694-109">To create a custom federated binding without secure session</span></span>

1. <span data-ttu-id="44694-110">Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSFederationHttpBinding>-Klasse, sei es imperativ im Code oder durch das Laden einer Instanz aus der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="44694-110">Create an instance of the <xref:System.ServiceModel.WSFederationHttpBinding> class either imperatively in code or by loading one from the configuration file.</span></span>

2. <span data-ttu-id="44694-111">Klonen Sie <xref:System.ServiceModel.WSFederationHttpBinding> in <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="44694-111">Clone the <xref:System.ServiceModel.WSFederationHttpBinding> into a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>

3. <span data-ttu-id="44694-112">Suchen Sie <xref:System.ServiceModel.Channels.SecurityBindingElement> in <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="44694-112">Find the <xref:System.ServiceModel.Channels.SecurityBindingElement> in the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>

4. <span data-ttu-id="44694-113">Suchen Sie <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> in <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="44694-113">Find the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> in the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>

5. <span data-ttu-id="44694-114">Ersetzen Sie das ursprüngliche <xref:System.ServiceModel.Channels.SecurityBindingElement> durch das Bootstrap-Sicherheitsbindungselement aus <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="44694-114">Replace the original <xref:System.ServiceModel.Channels.SecurityBindingElement> with the bootstrap security binding element from the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.</span></span>

## <a name="example"></a><span data-ttu-id="44694-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="44694-115">Example</span></span>

<span data-ttu-id="44694-116">Mit dem folgenden Beispielcode wird eine benutzerdefinierte Verbundbindung ohne sichere Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="44694-116">This following example creates a custom federated binding without secure session.</span></span>

[!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
[!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="44694-117">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="44694-117">Compiling the Code</span></span>

- <span data-ttu-id="44694-118">Um das Codebeispiel zu kompilieren, erstellen Sie ein Projekt, das auf die System.ServiceModel.dll-Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="44694-118">To compile the code example, create a project that references the System.ServiceModel.dll assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="44694-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44694-119">See also</span></span>

- [<span data-ttu-id="44694-120">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="44694-120">Bindings and Security</span></span>](bindings-and-security.md)
