---
title: "Inhaltsbasierte Korrelation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f46a2b68-8d24-4122-bbee-9573fc3f9fb4
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Inhaltsbasierte Korrelation
Wenn Workflowdienste mit Clients und anderen Diensten kommunizieren, sind in den ausgetauschten Nachrichten häufig Daten enthalten, die eine Nachricht eindeutig mit einer bestimmten Instanz verknüpfen.  Die inhaltsbasierte Korrelation verwendet diese Daten in der Nachricht, z. B. eine Kundennummer oder Bestellt\-ID, um Nachrichten an die richtige Workflowinstanz weiterzuleiten.  In diesem Thema wird erklärt, wie Sie die inhaltsbasierte Korrelation in Workflows verwenden.  
  
## Verwenden der inhaltsbasierten Korrelation  
 Die inhaltsbasierte Korrelation wird verwendet, wenn ein Workflowdienst über mehrere Methoden verfügt, auf die von einem einzelnen Client zugegriffen wird, und ein Datenelement in den ausgetauschten Nachrichten die gewünschte Instanz angibt.  
  
> [!NOTE]
>  Die inhaltsbasierte Korrelation ist nützlich, wenn die Kontextkorrelation nicht verwendet werden kann, weil es sich bei der Bindung nicht um eine der unterstützten Bindungen für den Kontextaustausch handelt.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] die Kontextkorrelation finden Sie unter [Kontextaustausch](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md).  
  
 Jede bei dieser Kommunikation verwendete Messagingaktivität muss die Position der Daten in der Nachricht angeben, die die Instanz eindeutig identifizieren.  Dazu wird <xref:System.ServiceModel.MessageQuerySet> mit <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> oder <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> bereitgestellt, um die Nachricht nach einem oder mehreren Datenelementen abzufragen, die die Instanz eindeutig identifizieren.  
  
> [!WARNING]
>  Die Daten zur Identifikation der Instanz werden per Hash in einen Korrelationsschlüssel umgewandelt.  Dabei müssen Sie sicherstellen, dass die für die Korrelation verwendeten Daten eindeutig sind, da sonst Konflikte im Hashschlüssel auftreten und Nachrichten ggf. falsch weitergeleitet werden können.  Wenn eine Korrelation z. B. ausschließlich auf einem Kundennamen basiert, kann es zu einem Konflikt kommen, da es möglicherweise mehrere Kunden mit dem gleichen Namen gibt.  Der Doppelpunkt \(`:`\) darf nicht als Bestandteil der Daten verwendet werden, mit denen die Meldung korreliert wird, da hiermit bereits Schlüssel und Wert der Meldungsabfrage begrenzt werden, um die Zeichenfolge zu bilden, für die anschließend der Hashwert berechnet wird.  
  
 Im folgenden Beispiel gibt der ursprüngliche <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> in einem Workflowdienst eine `OrderId` zurück, die dann auf den Aufruf der folgenden <xref:System.ServiceModel.Activities.Receive>\-Aktivität im Workflowdienst hin vom Client zurück übergeben wird.  
  
 [!code-csharp[CFX_ContentCorrelation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#1)]  
  
 Im vorherigen Beispiel wird eine von der <xref:System.ServiceModel.Activities.SendReply>\-Antwort initialisierte inhaltsbasierte Korrelation veranschaulicht.  Der <xref:System.ServiceModel.MessageQuerySet> gibt an, dass die Dateneinheit, mit der nachfolgende Nachrichten an diesen Dienst identifiziert werden, die `OrderId` ist.  
  
 [!code-csharp[CFX_ContentCorrelation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#2)]  
  
 Die <xref:System.ServiceModel.Activities.Receive>\-Aktivität, die der <xref:System.ServiceModel.Activities.SendReply> im Workflow folgt, folgt der Korrelation, die von der <xref:System.ServiceModel.Activities.SendReply> initialisiert wurde.  Beide Aktivitäten haben den gleichen <xref:System.ServiceModel.Activities.CorrelationHandle>, aber jede hat einen eigenen <xref:System.ServiceModel.MessageQuerySet> und eine eigene <xref:System.ServiceModel.XPathMessageQuery>, die angeben, wo in der jeweiligen Nachricht die identifizierenden Daten enthalten sind.  Auf die die Korrelation initialisierende Aktivität hin wird dieser <xref:System.ServiceModel.MessageQuerySet> in der <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>\-Eigenschaft angegeben, und bei weiteren <xref:System.ServiceModel.Activities.Receive>\-Aktivitäten wird er mit der <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>\-Eigenschaft angegeben.  
  
 [!code-csharp[CFX_ContentCorrelation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#3)]  
  
 Eine inhaltsbasierte Korrelation kann von jeder Messagingaktivität \(<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.ReceiveReply>\) initialisiert werden, wenn die Daten als Teil einer Nachricht weitergegeben werden.  Wenn die entsprechenden Daten nicht als Teil einer Nachricht weitergegeben werden, können sie unter Verwendung der <xref:System.ServiceModel.Activities.InitializeCorrelation>\-Aktivität ausdrücklich initialisiert werden.  Wenn zur eindeutigen Identifizierung der Nachricht verschiedene Daten erforderlich sind, können dem <xref:System.ServiceModel.MessageQuerySet> mehrere Abfragen hinzugefügt werden.  In diesen Beispielen wurde ein <xref:System.ServiceModel.Activities.CorrelationHandle> explizit für jede der Aktivitäten bereitgestellt, die die `CorrelatesWith`\-Eigenschaft oder die `CorrelationHandle`\-Eigenschaft verwenden, aber wenn nur eine Korrelation für den ganzen Workflow erforderlich ist, z. B. in diesem Beispiel, wo alles mit `OrderId` korreliert, ist die von <xref:System.ServiceModel.Activities.WorkflowServiceHost> bereitgestellte implizite Korrelationshandleverwaltung ausreichend.  
  
## Verwenden der InitializeCorrelation\-Aktivität  
 Im vorherigen Beispiel wurde die `OrderId` durch die <xref:System.ServiceModel.Activities.SendReply>\-Aktivität an den Aufrufer weitergegeben, und hier wurde die Korrelation initialisiert.  Das gleiche Verhalten kann mit der <xref:System.ServiceModel.Activities.InitializeCorrelation>\-Aktivität erreicht werden.  Die <xref:System.ServiceModel.Activities.InitializeCorrelation>\-Aktivität akzeptiert den <xref:System.ServiceModel.Activities.CorrelationHandle> und ein Wörterbuch von Elementen, die die Daten darstellen, mit denen die Nachricht der richtigen Instanz zugeordnet wird.  Um im vorhergehenden Beispiel die <xref:System.ServiceModel.Activities.InitializeCorrelation>\-Aktivität zu verwenden, entfernen Sie die <xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A> aus der <xref:System.ServiceModel.Activities.SendReply>\-Aktivität, und initialisieren Sie die Korrelation mit der <xref:System.ServiceModel.Activities.InitializeCorrelation>\-Aktivität.  
  
 [!code-csharp[CFX_ContentCorrelation#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#4)]  
  
 Die <xref:System.ServiceModel.Activities.InitializeCorrelation>\-Aktivität wird dann im Workflow verwendet, nachdem die die Daten enthaltenden Variablen aufgefüllt wurden, aber vor der <xref:System.ServiceModel.Activities.Receive>\-Aktivität, die dem initialisierten <xref:System.ServiceModel.Activities.CorrelationHandle> entspricht.  
  
 [!code-csharp[CFX_ContentCorrelation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#5)]  
  
## Konfigurieren von XPath\-Abfragen mit Workflow\-Designer  
 In den vorherigen Beispielen wurden die in der Nachricht verwendeten Aktivitäten und XPath\-Abfragen im Code angegeben.  Der Workflow\-Designer in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] bietet auch die Möglichkeit, XPaths aus `DataContract`\-Typen für inhaltsbasierte Korrelation zu generieren.  Der erste im vorherigen Beispiel konfigurierte XPath wurde für die <xref:System.ServiceModel.Activities.SendReply> konfiguriert.  
  
 [!code-csharp[CFX_ContentCorrelation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#2)]  
  
 Um den XPath für eine Messagingaktivität im Workflow\-Designer zu konfigurieren, wählen Sie die Aktivität im Workflow\-Designer aus.  Wenn die Aktivität die Korrelation initialisiert, wie im vorherigen Beispiel, klicken Sie im Eigenschaftenfenster auf die Schaltfläche mit den Auslassungspunkten für die **CorrelationInitializers**\-Eigenschaft.  Hierdurch wird das Dialogfeld **Korrelationsinitialisierer hinzufügen** angezeigt.  In diesem Dialogfeld können Sie die Korrelationsart angeben und den Inhalt auswählen, der für die Korrelation verwendet werden soll.  Die <xref:System.ServiceModel.Activities.CorrelationHandle>\-Variable wird im Feld **Initialisierer hinzufügen** angegeben. Der Typ und die Daten der Korrelation werden im Abschnitt **XPath\-Abfragen** des Dialogfelds ausgewählt.  
  
 ![CorrelationInitializer&#45;Dialogfeld](../../../../docs/framework/wcf/feature-details/media/correlationinitializerdlg.jpg "CorrelationInitializerDlg")  
  
 Die zweite XPath\-Abfrage im vorherigen Beispiel wurde in der <xref:System.ServiceModel.Activities.Receive>\-Aktivität konfiguriert.  
  
 [!code-csharp[CFX_ContentCorrelation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_contentcorrelation/cs/program.cs#3)]  
  
 Um die XPath\-Abfrage für eine Messagingaktivität zu konfigurieren, die nicht die Korrelation initialisiert, wählen Sie die Aktivität im Workflow\-Designer aus, und klicken Sie dann im Eigenschaftenfenster auf die Schaltfläche mit den Auslassungspunkten für die **CorrelatesOn**\-Eigenschaft.  Hierdurch wird das Dialogfeld **CorrelatesOn\-Definition** angezeigt.  
  
 ![CorrelatesOn&#45;Definition](../../../../docs/framework/wcf/feature-details/media/correlatesondialog.jpg "CorrelatesOnDialog")  
  
 In diesem Dialogfeld geben Sie den <xref:System.ServiceModel.Activities.CorrelationHandle> an und wählen Elemente in der Liste **XPath\-Abfragen** aus, um die XPath\-Abfrage zu erstellen.