---
title: 'Vorgehensweise: Zulassen von Metadatenanforderungen während der Autorisierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
ms.openlocfilehash: 9acc007ea7837f7b8e6c958fa81547fe4fa5b2c0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257612"
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a>Vorgehensweise: Zulassen von Metadatenanforderungen während der Autorisierung

Während der benutzerdefinierten Autorisierung ist es möglicherweise notwendig, eine Anforderung für Metadaten zuzulassen, die verarbeitet werden sollten. Das folgende Thema durchläuft die Schritte, um so eine Anforderung zu überprüfen.  
  
 Weitere Informationen zur Windows Communication Foundation (WCF)-Autorisierung finden Sie unter [Autorisierung](authorization-in-wcf.md).  
  
### <a name="to-allow-metadata-requests-during-authorization"></a>So lassen Sie Metadatenanforderungen während der Autorisierung zu  
  
1. Erstellen Sie eine Erweiterung der <xref:System.ServiceModel.ServiceAuthorizationManager>-Klasse.  
  
2. Überschreiben Sie die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> -Methode. Die Methode gibt `true` oder `false` abhängig davon zurück, ob Autorisierung zugelassen wird. Informationen zur aktuellen Prozedur finden Sie im <xref:System.ServiceModel.OperationContext>, der zur Methode als Parameter übergeben wird.  
  
3. Überprüfen Sie in der Außerkraftsetzung den Vertragsnamen, Namespace und die Aktion, wie im folgenden Beispiel gezeigt. Wenn die Bedingungen gültig sind, geben Sie `true.` zurück  
  
4. Verwenden Sie den Erweiterbarkeitspunkt, um die Klasse bereitzustellen. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel zeigt das Außerkraftsetzen der <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>-Methode.  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [Autorisierung](authorization-in-wcf.md)
- [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](managing-claims-and-authorization-with-the-identity-model.md)
