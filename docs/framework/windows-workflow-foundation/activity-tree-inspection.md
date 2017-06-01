---
title: "Aktivit&#228;tsstruktur&#252;berpr&#252;fung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 100d00e4-8c1d-4233-8fbb-dd443a01155d
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Aktivit&#228;tsstruktur&#252;berpr&#252;fung
Die Aktivitätsstrukturüberprüfung wird von Workflowanwendungsautoren verwendet, um die von der Anwendung gehosteten Workflows zu überprüfen.<xref:System.Activities.WorkflowInspectionServices> ermöglicht die Suche nach bestimmten untergeordneten Aktivitäten in Workflows, die Auflistung einzelner Aktivitäten und ihrer Eigenschaften sowie die Zwischenspeicherung von Laufzeitmetadaten der Aktivitäten zu einem bestimmten Zeitpunkt.Dieses Thema bietet eine Übersicht über <xref:System.Activities.WorkflowInspectionServices> und die Verwendung zur Überprüfung einer Aktivitätsstruktur.  
  
## Verwenden von WorkflowInspectionServices  
 Die <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>\-Methode wird verwendet, um alle Aktivitäten in der angegebenen Aktivitätsstruktur aufzulisten.<xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> gibt ein aufzählbares Element zurück, das alle Aktivitäten in der Struktur umfasst, darunter untergeordnete Elemente, Delegathandler, variable Standardwerte und Argumentausdrücke.Im folgenden Beispiel wird eine Workflowdefinition mithilfe der Elemente <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.WriteLine> und Ausdrücken erstellt.Nachdem die Workflowdefinition erstellt wurde, wird sie aufgerufen. Anschließend wird die `InspectActivity`\-Methode aufgerufen.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#45](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#45)]  
  
 Zur Auflistung der Aktivitäten wird <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> für die Stammaktivität und dann erneut rekursiv für jede zurückgegebene Aktivität aufgerufen.Im folgenden Beispiel wird das <xref:System.Activities.Activity.DisplayName%2A>\-Objekt von den einzelnen Aktivitäten und Ausdrücken in der Aktivitätsstruktur in die Konsole geschrieben.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#46](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#46)]  
  
 Mit diesem Beispielcode wird die folgende Ausgabe erzeugt.  
  
 **Listenelement 1**   
**Listenelement 2**   
**Listenelement 3**   
**Listenelement 4**   
**Listenelement 5**   
**Der Auflistung hinzugefügte Elemente.**   
**Sequenz**   
 **Literal\<List\<String\>\>**   
 **While**   
 **AddToCollection\<String\>**   
 **VariableValue\<ICollection\<String\>\>**   
 **LambdaValue\<String\>**   
 **LocationReferenceValue\<List\<String\>\>**   
 **LambdaValue\<Boolean\>**   
 **LocationReferenceValue\<List\<String\>\>**   
 **ForEach\<String\>**   
 **VariableValue\<IEnumerable\<String\>\>**   
 **WriteLine**   
 **DelegateArgumentValue\<String\>**   
 **Sequenz**   
 **WriteLine**   
 **Literal\<String\>**  Um eine bestimmte Aktivität abzurufen, statt alle Aktivitäten aufzulisten, wird <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> verwendet.Sowohl mit <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> als auch mit <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> wird die Zwischenspeicherung von Metadaten ausgeführt, wenn `WorkflowInspectionServices.CacheMetadata` zuvor nicht aufgerufen wurde.Wenn <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> aufgerufen wurde, basiert <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> auf den vorhandenen Metadaten.Falls also seit dem letzten Aufruf von <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> Strukturänderungen vorgenommen wurden, kann <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> zu unerwarteten Ergebnissen führen.Wenn nach dem Aufruf von <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> Änderungen am Workflow vorgenommen wurden, können Metadaten durch Aufrufen der <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>\-Methode erneut zwischengespeichert werden.Das Zwischenspeichern von Metadaten wird im nächsten Abschnitt erläutert.  
  
### Zwischenspeichern von Metadaten  
 Durch die Zwischenspeicherung der Metadaten für eine Aktivität wird eine Beschreibung der Argumente, Variablen, untergeordneten Aktivitäten und Aktivitätsdelegaten der Aktivität erstellt und validiert.Metadaten werden standardmäßig von der Laufzeit zwischengespeichert, wenn eine Aktivität zur Ausführung vorbereitet wird.Wenn ein Workflowhostautor die Metadaten für eine Aktivität oder eine Aktivitätsstruktur vorher zwischenspeichern möchte, um beispielsweise den gesamten Aufwand im Voraus zu erfassen, kann <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> verwendet werden, um die Metadaten zu dem gewünschten Zeitpunkt zwischenzuspeichern.