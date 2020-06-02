---
title: Ersetzen eines Principalobjekts
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
ms.openlocfilehash: 056bd0bbafe0e7dc84d8d0c532ff844370c59230
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291213"
---
# <a name="replacing-a-principal-object"></a><span data-ttu-id="dd511-102">Ersetzen eines Principalobjekts</span><span class="sxs-lookup"><span data-stu-id="dd511-102">Replacing a Principal Object</span></span>
<span data-ttu-id="dd511-103">Anwendungen, die Authentifizierungsdienste bereitstellen, müssen das **Principal** -Objekt (<xref:System.Security.Principal.IPrincipal>) für einen vorhandenen Thread ersetzen können.</span><span class="sxs-lookup"><span data-stu-id="dd511-103">Applications that provide authentication services must be able to replace the **Principal** object (<xref:System.Security.Principal.IPrincipal>) for a given thread.</span></span> <span data-ttu-id="dd511-104">Zusätzlich muss das Sicherheitssystem Schutz für ein Ersetzen von **Principal** -Objekten bieten, weil ein in böswilliger Absicht zugewiesenes falsches **Principal** -Objekt die Sicherheit der Anwendung durch Angabe einer falschen Identität oder Rolle beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="dd511-104">Furthermore, the security system must help protect the ability to replace **Principal** objects because a maliciously attached, incorrect **Principal** compromises the security of your application by claiming an untrue identity or role.</span></span> <span data-ttu-id="dd511-105">Daher muss Anwendungen, die in der Lage sind, **Principal** -Objekte zu ersetzen, das <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> -Objekt gewährt werden, damit Prinzipale gesteuert werden können.</span><span class="sxs-lookup"><span data-stu-id="dd511-105">Therefore, applications that require the ability to replace **Principal** objects must be granted the <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> object for principal control.</span></span> <span data-ttu-id="dd511-106">(Beachten Sie, dass diese Berechtigung nicht dazu erforderlich ist, rollenbasierte Sicherheitsüberprüfungen auszuführen oder **Principal** -Objekte zu erstellen.)</span><span class="sxs-lookup"><span data-stu-id="dd511-106">(Note that this permission is not required for performing role-based security checks or for creating **Principal** objects.)</span></span>  
  
 <span data-ttu-id="dd511-107">Das aktuelle **Principal** -Objekt kann ersetzt werden, indem die folgenden Schritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="dd511-107">The current **Principal** object can be replaced by performing the following tasks:</span></span>  
  
1. <span data-ttu-id="dd511-108">Erstellen Sie das ersetzende **Principal** -Objekt und das zugeordnete **Identity** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="dd511-108">Create the replacement **Principal** object and associated **Identity** object.</span></span>  
  
2. <span data-ttu-id="dd511-109">Ordnen Sie das neue **Principal** -Objekt dem Aufrufkontext zu.</span><span class="sxs-lookup"><span data-stu-id="dd511-109">Attach the new **Principal** object to the call context.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd511-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd511-110">Example</span></span>  
 <span data-ttu-id="dd511-111">Im folgenden Beispiel wird veranschaulicht, wie ein allgemeines Principal-Objekt erstellt und dann dazu verwendet wird, den Prinzipal eines Threads festzulegen.</span><span class="sxs-lookup"><span data-stu-id="dd511-111">The following example shows how to create a generic principal object and use it to set the principal of a thread.</span></span>  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="dd511-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd511-112">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>
- [<span data-ttu-id="dd511-113">Principal- und Identitätsobjekte</span><span class="sxs-lookup"><span data-stu-id="dd511-113">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
