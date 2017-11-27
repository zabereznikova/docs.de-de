---
title: "Aktivitätsstrukturüberprüfung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 100d00e4-8c1d-4233-8fbb-dd443a01155d
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5a93b2d46dee3aab963e7ec97618661435e18def
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="activity-tree-inspection"></a>Aktivitätsstrukturüberprüfung
Die Aktivitätsstrukturüberprüfung wird von Workflowanwendungsautoren verwendet, um die von der Anwendung gehosteten Workflows zu überprüfen. <xref:System.Activities.WorkflowInspectionServices> ermöglicht die Suche nach bestimmten untergeordneten Aktivitäten in Workflows, die Auflistung einzelner Aktivitäten und ihrer Eigenschaften sowie die Zwischenspeicherung von Laufzeitmetadaten der Aktivitäten zu einem bestimmten Zeitpunkt. Dieses Thema bietet eine Übersicht über <xref:System.Activities.WorkflowInspectionServices> und die Verwendung zur Überprüfung einer Aktivitätsstruktur.  
  
## <a name="using-workflowinspectionservices"></a>Verwenden von WorkflowInspectionServices  
 Die <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>-Methode wird verwendet, um alle Aktivitäten in der angegebenen Aktivitätsstruktur aufzulisten. <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> gibt ein aufzählbares Element zurück, das alle Aktivitäten in der Struktur umfasst, darunter untergeordnete Elemente, Delegathandler, variable Standardwerte und Argumentausdrücke. Im folgenden Beispiel wird eine Workflowdefinition mithilfe der Elemente <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.WriteLine> und Ausdrücken erstellt. Nachdem die Workflowdefinition erstellt wurde, wird sie aufgerufen. Anschließend wird die `InspectActivity`-Methode aufgerufen.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#45](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#45)]  
  
 Zur Auflistung der Aktivitäten wird <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> für die Stammaktivität und dann erneut rekursiv für jede zurückgegebene Aktivität aufgerufen. Im folgenden Beispiel wird das <xref:System.Activities.Activity.DisplayName%2A>-Objekt von den einzelnen Aktivitäten und Ausdrücken in der Aktivitätsstruktur in die Konsole geschrieben.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#46](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#46)]  
  
 Mit diesem Beispielcode wird die folgende Ausgabe erzeugt.  
  
 **List-Item 1**  
**List-Item 2**   
**List-Item 3**   
**Listenelement 4**   
**Listenelement 5**   
**Elemente, die zur Auflistung hinzugefügt werden.**   
**Sequenz**   
 **Literal < Liste\<Zeichenfolge >>**  
 **While**  
 **AddToCollection\<Zeichenfolge >**  
 **VariableValue < ICollection\<Zeichenfolge >>**  
 **LambdaValue\<Zeichenfolge >**  
 **LocationReferenceValue < Liste\<Zeichenfolge >>**  
 **LambdaValue\<booleschen >**  
 **LocationReferenceValue < Liste\<Zeichenfolge >>**  
 **ForEach\<Zeichenfolge >**  
 **VariableValue < IEnumerable\<Zeichenfolge >>**  
 **WriteLine**  
 **DelegateArgumentValue\<Zeichenfolge >**  
 **Sequenz**  
 **WriteLine**  
 **Literal\<Zeichenfolge >** zum Abrufen einer bestimmten Aktivität anstatt alle Aktivitäten, <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> verwendet wird. Sowohl mit <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> als auch mit <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> wird die Zwischenspeicherung von Metadaten ausgeführt, wenn `WorkflowInspectionServices.CacheMetadata` zuvor nicht aufgerufen wurde. Wenn <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> aufgerufen wurde, basiert <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> auf den vorhandenen Metadaten. Falls also seit dem letzten Aufruf von <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> Strukturänderungen vorgenommen wurden, kann <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> zu unerwarteten Ergebnissen führen. Wenn Änderungen an den Workflow nach dem Aufruf vorgenommen wurden <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>, Metadaten kann erneut zwischengespeichert werden, durch Aufrufen der <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> Methode. Das Zwischenspeichern von Metadaten wird im nächsten Abschnitt erläutert.  
  
### <a name="caching-metadata"></a>Zwischenspeichern von Metadaten  
 Durch die Zwischenspeicherung der Metadaten für eine Aktivität wird eine Beschreibung der Argumente, Variablen, untergeordneten Aktivitäten und Aktivitätsdelegaten der Aktivität erstellt und validiert. Metadaten werden standardmäßig von der Laufzeit zwischengespeichert, wenn eine Aktivität zur Ausführung vorbereitet wird. Wenn ein Workflowhostautor die Metadaten für eine Aktivität oder eine Aktivitätsstruktur vorher zwischenspeichern möchte, um beispielsweise den gesamten Aufwand im Voraus zu erfassen, kann <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> verwendet werden, um die Metadaten zu dem gewünschten Zeitpunkt zwischenzuspeichern.
