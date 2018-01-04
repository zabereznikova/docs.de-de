---
title: Ersetzen eines Principalobjekts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c53064ae12889df09b5259fbb7c8159cfdcd07aa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="replacing-a-principal-object"></a>Ersetzen eines Principalobjekts
Anwendungen, die Authentifizierungsdienste bereitstellen, müssen das **Principal** -Objekt (<xref:System.Security.Principal.IPrincipal>) für einen vorhandenen Thread ersetzen können. Zusätzlich muss das Sicherheitssystem Schutz für ein Ersetzen von **Principal** -Objekten bieten, weil ein in böswilliger Absicht zugewiesenes falsches **Principal** -Objekt die Sicherheit der Anwendung durch Angabe einer falschen Identität oder Rolle beeinträchtigt. Aus diesem Grund Anwendungen, die erfordern die Fähigkeit zum Ersetzen **Principal** Objekte gewährt werden die <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> Objekt damit Prinzipale gesteuert. (Beachten Sie, dass diese Berechtigung nicht dazu erforderlich ist, rollenbasierte Sicherheitsüberprüfungen auszuführen oder **Principal** -Objekte zu erstellen.)  
  
 Das aktuelle **Principal** -Objekt kann ersetzt werden, indem die folgenden Schritte ausgeführt werden:  
  
1.  Erstellen Sie das ersetzende **Principal** -Objekt und das zugeordnete **Identity** -Objekt.  
  
2.  Ordnen Sie das neue **Principal** -Objekt dem Aufrufkontext zu.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein allgemeines Principal-Objekt erstellt und dann dazu verwendet wird, den Prinzipal eines Threads festzulegen.  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>  
 [Principal- und Identitätsobjekte](../../../docs/standard/security/principal-and-identity-objects.md)
