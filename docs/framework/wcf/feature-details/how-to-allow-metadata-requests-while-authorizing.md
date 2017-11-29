---
title: "Gewusst wie: Zulassen von Metadatenanforderungen während der Autorisierung"
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
helpviewer_keywords: allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 103aba5118810064c1cafb7c82634ef000ced667
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a>Gewusst wie: Zulassen von Metadatenanforderungen während der Autorisierung
Während der benutzerdefinierten Autorisierung ist es möglicherweise notwendig, eine Anforderung für Metadaten zuzulassen, die verarbeitet werden sollten. Das folgende Thema durchläuft die Schritte, um so eine Anforderung zu überprüfen.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Autorisierung finden Sie unter [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
### <a name="to-allow-metadata-requests-during-authorization"></a>So lassen Sie Metadatenanforderungen während der Autorisierung zu  
  
1.  Erstellen Sie eine Erweiterung der <xref:System.ServiceModel.ServiceAuthorizationManager>-Klasse.  
  
2.  Überschreiben Sie die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>-Methode. Die Methode gibt `true` oder `false` abhängig davon zurück, ob Autorisierung zugelassen wird. Informationen zur aktuellen Prozedur finden Sie im <xref:System.ServiceModel.OperationContext>, der zur Methode als Parameter übergeben wird.  
  
3.  Überprüfen Sie in der Außerkraftsetzung den Vertragsnamen, Namespace und die Aktion, wie im folgenden Beispiel gezeigt. Wenn die Bedingungen gültig sind, geben Sie `true.` zurück  
  
4.  Verwenden Sie den Erweiterbarkeitspunkt, um die Klasse bereitzustellen. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Außerkraftsetzen der <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>-Methode.  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
