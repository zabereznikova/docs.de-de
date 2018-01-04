---
title: "Vorgehensweise: Ansprüche vergleichen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], comparing
- claims [WCF]
ms.assetid: 0c4ec84d-53df-408f-8953-9bc437f56c28
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf7a621a7aa457b2993c761caa2ad576d216638b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-compare-claims"></a>Vorgehensweise: Ansprüche vergleichen
Die Identitätsmodellinfrastruktur in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] wird verwendet, um die Autorisierungsüberprüfung auszuführen. Eine gängige Aufgabe besteht darin, die Ansprüche im Autorisierungskontext mit den Ansprüchen zu vergleichen, die erforderlich sind, um die angeforderte Aktion auszuführen oder auf die angeforderte Ressource zuzugreifen. In diesem Thema wird beschrieben, wie Ansprüche verglichen werden, einschließlich integrierter und benutzerdefinierter Anspruchstypen. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]die identitätsmodellinfrastruktur finden Sie unter [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).  
  
 Der Vergleich von Ansprüchen umfasst das Vergleichen der drei Bestandteile des Anspruchs (Typ, Recht und Ressource) mit den entsprechenden Teilen eines anderen Anspruchs, um festzustellen, ob sie identisch sind. Weitere Informationen finden Sie im folgenden Beispiel.  
  
 [!code-csharp[c_CustomClaimComparison#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#9)]
 [!code-vb[c_CustomClaimComparison#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#9)]  
  
 Beide Ansprüche haben den Anspruchstyp <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, das Recht <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> und eine Ressource der Zeichenfolge "someone". Da alle drei Teile des Anspruchs gleich sind, sind die Ansprüche identisch.  
  
 Die integrierten Anspruchstypen werden mit der <xref:System.IdentityModel.Claims.Claim.Equals%2A>-Methode verglichen. Anspruchsspezifischer Vergleichscode wird verwendet, falls erforderlich. Es liegen z. B. die folgenden zwei Benutzerprinzipalnamen (UPN)-Ansprüche vor:  
  
 [!code-csharp[c_CustomClaimComparison#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#4)]
 [!code-vb[c_CustomClaimComparison#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#4)]  
  
 der Vergleichscode in der <xref:System.IdentityModel.Claims.Claim.Equals%2A> -Methode zurückkehrt `true`davon ausgegangen, dass `example\someone` identifiziert den gleiche Domänenbenutzer als "someone@example.com".  
  
 Benutzerdefinierte Anspruchstypen können auch mit der <xref:System.IdentityModel.Claims.Claim.Equals%2A>-Methode verglichen werden. In Fällen, in denen der von der <xref:System.IdentityModel.Claims.Claim.Resource%2A>-Eigenschaft des Anspruchs zurückgegebene Typ kein primitiver Typ ist, gibt <xref:System.IdentityModel.Claims.Claim.Equals%2A> nur `true` zurück, wenn die von den `Resource`-Eigenschaften zurückgegebenen Werte laut der <xref:System.IdentityModel.Claims.Claim.Equals%2A>-Methode identisch sind. In Fällen, in denen dies nicht zutrifft, überschreibt der von der `Resource`-Eigenschaft zurückgegebene benutzerdefinierte Typ die <xref:System.IdentityModel.Claims.Claim.Equals%2A>-Methode und die <xref:System.Object.GetHashCode%2A>-Methode, um die erforderliche benutzerdefinierte Verarbeitung auszuführen.  
  
### <a name="comparing-built-in-claims"></a>Vergleichen von integrierten Ansprüchen  
  
1.  Wenn zwei Instanzen der <xref:System.IdentityModel.Claims.Claim>-Klasse vorliegen, verwenden Sie <xref:System.IdentityModel.Claims.Claim.Equals%2A> für den Vergleich, wie im folgenden Code gezeigt.  
  
     [!code-csharp[c_CustomClaimComparison#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#5)]
     [!code-vb[c_CustomClaimComparison#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#5)]  
  
### <a name="comparing-custom-claims-with-primitive-resource-types"></a>Vergleichen von benutzerdefinierten Ansprüchen mit primitiven Ressourcentypen  
  
1.  Für benutzerdefinierte Ansprüche mit primitiven Ressourcentypen kann der Vergleich wie für integrierte Ansprüche erfolgen, wie im folgenden Code veranschaulicht.  
  
     [!code-csharp[c_CustomClaimComparison#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#6)]
     [!code-vb[c_CustomClaimComparison#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#6)]  
  
2.  Für benutzerdefinierte Ansprüche mit struktur- oder klassenbasierten Typen überschreibt der Ressourcentyp die <xref:System.IdentityModel.Claims.Claim.Equals%2A>-Methode.  
  
3.  Überprüfen Sie zunächst, ob der `obj`-Parameter `null` ist, und wenn ja, geben Sie `false` zurück.  
  
     [!code-csharp[c_CustomClaimComparison#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#7)]
     [!code-vb[c_CustomClaimComparison#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#7)]  
  
4.  Rufen Sie als nächstes <xref:System.Object.ReferenceEquals%2A> auf, und übergeben Sie `this` und `obj` als Parameter. Wenn `true` zurückgegeben wird, geben Sie `true` zurück.  
  
     [!code-csharp[c_CustomClaimComparison#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#8)]
     [!code-vb[c_CustomClaimComparison#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#8)]  
  
5.  Versuchen Sie danach, `obj` einer lokalen Variable des Klassentyps zuzuweisen. Wenn dieser Versuch fehlschlägt, lautet die Referenz `null`. In derartigen Fällen wird `false` zurückgegeben.  
  
6.  Führen Sie den benutzerdefinierten Vergleich durch, der notwendig ist, um den aktuellen Anspruch ordnungsgemäß mit dem bereitgestellten Anspruch zu vergleichen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen Vergleich von benutzerdefinierten Ansprüchen, deren Anspruchsressource ein nicht primitiver Typ ist.  
  
 [!code-csharp[c_CustomClaimComparison#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#0)]
 [!code-vb[c_CustomClaimComparison#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#0)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [Vorgehensweise: Erstellen eines benutzerdefinierten Anspruchs](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
