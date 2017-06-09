---
title: "Hierarchisches Konfigurationsmodell | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Hierarchisches Konfigurationsmodell
In diesem Beispiel wird veranschaulicht, wie eine Hierarchie von Konfigurationsdateien für Dienste implementiert wird.Es wird auch gezeigt, wie Bindungen, Dienstverhalten und Endpunktverhalten von höheren Ebenen in der Hierarchie geerbt werden.  
  
## Beispieldetails  
 Eine der Funktionen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] entwickelt wurden, besteht in der Verbesserung des hierarchischen Konfigurationsmodells.Ein hierarchisches Konfigurationsmodell ist z. B. das Modell, das von Machine.config \-\> Rootweb.config \-\> Web.config definiert wurde.In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] werden die Bindungen und Verhaltensweisen, die in den oberen Ebenen der Konfigurationshierarchie definiert werden, zum Dienst ohne explizite Konfiguration hinzugefügt.In diesem Beispiel wird gezeigt, wie die Dienstkonfiguration basierend auf Konfigurationselementen vereinfacht werden kann, die auf Computer\- oder Anwendungsebene definiert sind.  
  
 Dieses Beispiel umfasst neun Dienste, die in drei Hierarchieebenen definiert sind.`Service1` befindet sich auf Stammebene.`Service2` und `Service3` erben die Standardelemente von `Service1`.`Service4`, `Service5`, `Service6` und `Service7` werden auf einer dritten Ebene der Hierarchie definiert und erben die Standardelemente von `Service3`.`Service10` und `Service11` befinden sich schließlich auf einer vierten Ebene der Hierarchie.  
  
 Alle Dienste implementieren den `IDesc`\-Vertrag.Nachfolgend wird die Definition der `IDesc`\-Schnittstelle mit den in dieser Schnittstelle verfügbar gemachten Methoden anzeigt.Die `IDesc`\-Schnittstelle wird in Service1.cs definiert.  
  
```  
// Define a service contract  
[ServiceContract(Namespace="http://Microsoft.Samples.ConfigHierarchicalModel")]  
public interface IDesc  
{  
    [OperationContract]  
    List<string> ListEndpoints();  
    [OperationContract]  
    List<string> ListServiceBehaviors();  
    [OperationContract]  
    List<string> ListEndpointBehaviors();  
}  
  
```  
  
 Die Implementierung dieser Methoden durch die Dienste ist einfach.`ListEndpoints` durchläuft alle Dienstendpunkte und gibt eine Liste aller Endpunkte des Diensts zurück.`ListServiceBehaviors` durchläuft alle dem Dienst hinzugefügten Verhaltensweisen und gibt eine Liste mit allen dem Dienst zugeordneten Dienstverhaltensweisen zurück.`ListEndpointBehaviors` verhält sich ähnlich wie `ListServiceBehaviors`, gibt jedoch eine Liste mit Verhaltensweisen von Endpunkten zurück.  
  
 Diese Implementierung ermöglicht es, dass der Client die Anzahl der vom Dienst verfügbar gemachten Endpunkte und die dem Dienst hinzugefügten Verhaltensweisen und Endpunktverhaltensweisen kennt.Der Client, der als Teil des Beispiels implementiert wurde, fügt allen Diensten in der Projektmappe einen Dienstverweis hinzu und zeigt diese Elemente für jeden der Dienste an.  
  
## So verwenden Sie dieses Beispiel  
  
#### So führen Sie den Client aus  
  
1.  Öffnen Sie die Datei ConfigHierarchicalModel.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Wenn das Clientprojekt nicht bereits als Startprojekt eingerichtet ist, führen Sie folgende Schritte aus.  
  
    1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie dann die Option **Eigenschaften** aus.  
  
    2.  Wählen Sie unter **Allgemeine Eigenschaften** die Option **Startprojekt** aus, und klicken Sie dann auf **Einzelnes Startprojekt**.  
  
    3.  Wählen Sie in der Dropdownliste **Einzelnes Startprojekt** die Option **Client** aus.  
  
    4.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
3.  Drücken Sie STRG\+UMSCHALT\+B, um das Beispiel zu erstellen.  
  
4.  Drücken Sie STRG \+ F5, um den Client auszuführen.  
  
> [!NOTE]
>  Wenn diese Schritte nicht funktionieren, stellen Sie mithilfe der folgenden Schritte sicher, dass die Umgebung ordnungsgemäß eingerichtet wurde.  
>   
>  1.  Vergewissern Sie sich, dass Sie [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
> 2.  Folgen Sie den unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen, um die Projektmappe zu erstellen.  
> 3.  Wenn Sie das Beispiel in einer Konfiguration mit einem Computer oder mehreren Computern ausführen möchten, folgen Sie den unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md) aufgeführten Anweisungen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## Siehe auch  
 [AppFabric\-Verwaltungsbeispiele](http://go.microsoft.com/fwlink/?LinkId=193960)