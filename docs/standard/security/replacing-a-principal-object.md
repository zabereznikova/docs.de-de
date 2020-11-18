---
title: Ersetzen eines Principalobjekts
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET], replacing principal objects
- security [.NET], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
ms.openlocfilehash: b8f7a8fbd3b9c65126d6a3a65a5f6722f2ad93de
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824173"
---
# <a name="replacing-a-principal-object"></a>Ersetzen eines Principalobjekts

Anwendungen, die Authentifizierungsdienste bereitstellen, müssen das **Principal** -Objekt (<xref:System.Security.Principal.IPrincipal>) für einen vorhandenen Thread ersetzen können. Zusätzlich muss das Sicherheitssystem Schutz für ein Ersetzen von **Principal** -Objekten bieten, weil ein in böswilliger Absicht zugewiesenes falsches **Principal** -Objekt die Sicherheit der Anwendung durch Angabe einer falschen Identität oder Rolle beeinträchtigt. Daher muss Anwendungen, die in der Lage sind, **Principal** -Objekte zu ersetzen, das <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> -Objekt gewährt werden, damit Prinzipale gesteuert werden können. (Beachten Sie, dass diese Berechtigung nicht dazu erforderlich ist, rollenbasierte Sicherheitsüberprüfungen auszuführen oder **Principal** -Objekte zu erstellen.)  
  
Das aktuelle **Principal** -Objekt kann ersetzt werden, indem die folgenden Schritte ausgeführt werden:  
  
1. Erstellen Sie das ersetzende **Principal** -Objekt und das zugeordnete **Identity** -Objekt.  
  
2. Ordnen Sie das neue **Principal** -Objekt dem Aufrufkontext zu.  
  
## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein allgemeines Principal-Objekt erstellt und dann dazu verwendet wird, den Prinzipal eines Threads festzulegen.  
  
[!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
[!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>
- [Principal- und Identitätsobjekte](principal-and-identity-objects.md)
- [ASP.net Core Sicherheit](/aspnet/core/security/)
