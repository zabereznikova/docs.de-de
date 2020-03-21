---
title: Angeben des Clientlaufzeitverhaltens
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- behaviors [WCF], system-provided client
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
ms.openlocfilehash: f9c22d25bedc36b3515538a8785b488aaa547990
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143238"
---
# <a name="specifying-client-run-time-behavior"></a>Angeben des Clientlaufzeitverhaltens
Windows Communication Foundation (WCF)-Clients können, wie z. B. Windows Communication Foundation (WCF)-Dienste, so konfiguriert werden, dass das Laufzeitverhalten an die Clientanwendung angepasst wird. Drei Attribute sind zum Angeben des Clientlaufzeitverhaltens verfügbar. Duplexclient-Rückrufobjekte können das <xref:System.ServiceModel.CallbackBehaviorAttribute>-Attribut und das <xref:System.ServiceModel.Description.CallbackDebugBehavior>-Attribut verwenden, um ihr Laufzeitverhalten zu ändern. Das andere Attribut, <xref:System.ServiceModel.Description.ClientViaBehavior>, kann verwendet werden, um das logische Ziel vom unmittelbaren Netzwerkziel zu trennen. Außerdem können Duplexclient-Rückruftypen Teile des Dienstseitenverhaltens verwenden. Weitere Informationen finden Sie unter [Angeben des Dienstlaufzeitverhaltens](specifying-service-run-time-behavior.md).  
  
## <a name="using-the-callbackbehaviorattribute"></a>Verwenden des CallbackBehaviorAttribute  
 Sie können das Ausführungsverhalten einer Rückrufvertragsimplementierung in einer Clientanwendung mit der <xref:System.ServiceModel.CallbackBehaviorAttribute>-Klasse konfigurieren oder erweitern. Dieses Attribut führt eine ähnliche Funktion für die Rückrufklasse wie die <xref:System.ServiceModel.ServiceBehaviorAttribute>-Klasse aus, das Instanziieren von Verhaltens- und Transaktionseinstellungen ausgenommen.  
  
 Die <xref:System.ServiceModel.CallbackBehaviorAttribute>-Klasse muss auf die Klasse angewendet werden, die den Rückrufvertrag implementiert. Beim Anwenden auf eine Nicht-Duplex-Vertragsimplementierung wird zur Laufzeit eine <xref:System.InvalidOperationException>-Ausnahme ausgelöst. Das folgende Codebeispiel zeigt eine <xref:System.ServiceModel.CallbackBehaviorAttribute>-Klasse für ein Rückrufobjekt, das das <xref:System.Threading.SynchronizationContext>-Objekt zur Bestimmung des Threads für das Marshallen verwendet, die <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A>-Eigenschaft zum Erzwingen der Nachrichtenvalidierung und die <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A>-Eigenschaft zum Zurückgeben von Ausnahmen als <xref:System.ServiceModel.FaultException>-Objekte an den Dienst zum Debuggen.  
  
 [!code-csharp[CallbackBehaviorAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/callbackbehaviorattribute/cs/client.cs#3)]
 [!code-vb[CallbackBehaviorAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/callbackbehaviorattribute/vb/client.vb#3)]  
  
## <a name="using-callbackdebugbehavior-to-enable-the-flow-of-managed-exception-information"></a>Verwenden von CallbackDebugBehavior zum Aktivieren des Flusses verwalteter Ausnahmeinformationen  
 Sie können den Fluss verwalteter Ausnahmeinformationen in einem Client-Rückrufobjekt zurück zum Dienst zum Debuggen aktivieren, indem Sie die <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A>-Eigenschaft entweder programmgesteuert oder aus einer Anwendungskonfigurationsdatei auf `true` festlegen.  
  
 Verwaltete Ausnahmeinformationen an Dienste zurückzugeben, kann ein Sicherheitsrisiko darstellen, da Ausnahmedetails Informationen zur internen Clientimplementierung offen legen, die von nicht autorisierten Diensten verwendet werden können. Außerdem wird, obwohl die <xref:System.ServiceModel.Description.CallbackDebugBehavior>-Eigenschaften auch programmgesteuert festgelegt werden können, bei der Bereitstellung das Deaktivieren von <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> schnell vergessen.  
  
 Wegen der damit verbundenen Sicherheitsprobleme wird Folgendes dringend empfohlen:  
  
- Verwenden Sie eine Anwendungskonfigurationsdatei, um den Wert der <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A>-Eigenschaft auf `true` festzulegen.  
  
- Führen Sie diesen Vorgang nur in gesteuerten Debugszenarien aus.  
  
 Das folgende Codebeispiel zeigt eine Clientkonfigurationsdatei, die WCF anweist, verwaltete Ausnahmeinformationen von einem Clientrückrufobjekt in SOAP-Nachrichten zurückzugeben.  
  
 [!code-xml[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]  

## <a name="using-the-clientviabehavior-behavior"></a>Verwenden des ClientViaBehavior-Verhaltens  
 Sie können mit dem <xref:System.ServiceModel.Description.ClientViaBehavior>-Verhalten den URI (Uniform Resource Identifier) angeben, für den der Transportkanal erstellt werden soll. Verwenden Sie dieses Verhalten, wenn das unmittelbare Netzwerkziel nicht der gewünschte Prozessor der Nachricht ist. Dies ermöglicht Konversationen über mehrere Hops, wenn die aufrufende Anwendung das endgültige Ziel nicht unbedingt kennt oder wenn der `Via`-Header des Ziels keine Adresse ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Angeben des Dienstlaufzeitverhaltens](specifying-service-run-time-behavior.md)
