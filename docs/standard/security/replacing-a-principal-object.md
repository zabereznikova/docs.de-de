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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f33be207dd6166b16a04844f3d92b6e017d1c7a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018787"
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
- [Principal- und Identitätsobjekte](../../../docs/standard/security/principal-and-identity-objects.md)
