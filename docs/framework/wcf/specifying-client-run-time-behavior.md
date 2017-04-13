---
title: "Angeben des Clientlaufzeitverhaltens | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Verhalten [WCF], vom System bereitgestellter client"
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Angeben des Clientlaufzeitverhaltens
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Clients wie [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienste können so konfiguriert werden, dass sie das Laufzeitverhalten der Clientanwendung anpassen. Drei Attribute sind zum Angeben des Clientlaufzeitverhaltens verfügbar. Duplexclient-Rückrufobjekte können das <xref:System.ServiceModel.CallbackBehaviorAttribute> und <xref:System.ServiceModel.Description.CallbackDebugBehavior> Attribute, deren Verhalten zur Laufzeit zu ändern. Das andere Attribut <xref:System.ServiceModel.Description.ClientViaBehavior>, kann verwendet werden, um das logische Ziel vom unmittelbaren Netzwerkziel zu trennen. Außerdem können Duplexclient-Rückruftypen Teile des Dienstseitenverhaltens verwenden. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Laufzeit-Dienstverhalten angegeben](../../../docs/framework/wcf/specifying-service-run-time-behavior.md).  
  
## <a name="using-the-callbackbehaviorattribute"></a>Verwenden des CallbackBehaviorAttribute  
 Sie können konfigurieren oder Erweitern Sie das Ausführungsverhalten einer rückrufvertragsimplementierung in einer Clientanwendung mithilfe der <xref:System.ServiceModel.CallbackBehaviorAttribute> Klasse. Dieses Attribut führt eine ähnliche Funktion für die Rückrufklasse wie die <xref:System.ServiceModel.ServiceBehaviorAttribute> Klasse instanziieren von Verhaltens-und transaktionseinstellungen ausgenommen.  
  
 Die <xref:System.ServiceModel.CallbackBehaviorAttribute> Klasse muss auf die Klasse, die den Rückrufvertrag implementiert angewendet werden. Wenn eine vertragsimplementierung zugewiesen ein <xref:System.InvalidOperationException> Ausnahme zur Laufzeit. Das folgende Codebeispiel zeigt eine <xref:System.ServiceModel.CallbackBehaviorAttribute> Klasse für ein Rückrufobjekt, das verwendet die <xref:System.Threading.SynchronizationContext> Objekts bestimmen, den Thread für das Marshallen der <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> -Eigenschaft zum Erzwingen der nachrichtenvalidierung und die <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> -Eigenschaft zum Zurückgeben von Ausnahmen als <xref:System.ServiceModel.FaultException> -Objekte an den Dienst zum Debuggen.  
  
 [!code-csharp[CallbackBehaviorAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/callbackbehaviorattribute/cs/client.cs#3)]
 [!code-vb[CallbackBehaviorAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/callbackbehaviorattribute/vb/client.vb#3)]  
  
## <a name="using-callbackdebugbehavior-to-enable-the-flow-of-managed-exception-information"></a>Verwenden von CallbackDebugBehavior zum Aktivieren des Flusses verwalteter Ausnahmeinformationen  
 Sie können den Fluss verwalteter Ausnahmeinformationen in einem Client-Rückrufobjekt zurück an den Dienst für Debuggingzwecke durch Festlegen der <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> -Eigenschaft `true` entweder programmgesteuert oder aus einer Anwendungskonfigurationsdatei.  
  
 Verwaltete Ausnahmeinformationen an Dienste zurückzugeben, kann ein Sicherheitsrisiko darstellen, da Ausnahmedetails Informationen zur internen Clientimplementierung offen legen, die von nicht autorisierten Diensten verwendet werden können. Darüber hinaus auch die <xref:System.ServiceModel.Description.CallbackDebugBehavior> Eigenschaften können auch programmgesteuert festgelegt werden, es kann leicht vergessen, deaktivieren Sie <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> bei der Bereitstellung.  
  
 Wegen der damit verbundenen Sicherheitsprobleme wird Folgendes dringend empfohlen:  
  
-   Sie verwenden eine Anwendungskonfigurationsdatei zum Festlegen des Werts von der <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> -Eigenschaft `true`.  
  
-   Führen Sie diesen Vorgang nur in gesteuerten Debugszenarien aus.  
  
 Das folgende Codebeispiel zeigt eine Clientkonfigurationsdatei, die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] anweist, verwaltete Ausnahmeinformationen aus einem Client-Rückrufobjekt in SOAP-Nachrichten zurückzugeben.  
  
 [!code[SCA.CallbackContract#4](../../../samples/snippets/common/VS_Snippets_CFX/sca.callbackcontract/common/client.exe.config#4)]
 [!code-csharp[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]
 [!code-vb[SCA.CallbackContract#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.callbackcontract/vb/client.exe.config#4)]  
  
## <a name="using-the-clientviabehavior-behavior"></a>Verwenden des ClientViaBehavior-Verhaltens  
 Sie können die <xref:System.ServiceModel.Description.ClientViaBehavior> Verhalten an den Uniform Resource Identifier, für den der Transportkanal erstellt werden soll. Verwenden Sie dieses Verhalten, wenn das unmittelbare Netzwerkziel nicht der gewünschte Prozessor der Nachricht ist. Dies ermöglicht Konversationen über mehrere Hops, wenn die aufrufende Anwendung das endgültige Ziel nicht unbedingt kennt oder wenn der `Via`-Header des Ziels keine Adresse ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Angeben der Dienstlaufzeit Verhalten](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)