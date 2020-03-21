---
title: Aktivitätsstrukturüberprüfung
ms.date: 03/30/2017
ms.assetid: 100d00e4-8c1d-4233-8fbb-dd443a01155d
ms.openlocfilehash: 692f36d993c3f9c27839122b388a24d0698a2b59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183042"
---
# <a name="activity-tree-inspection"></a>Aktivitätsstrukturüberprüfung
Die Aktivitätsstrukturüberprüfung wird von Workflowanwendungsautoren verwendet, um die von der Anwendung gehosteten Workflows zu überprüfen. <xref:System.Activities.WorkflowInspectionServices> ermöglicht die Suche nach bestimmten untergeordneten Aktivitäten in Workflows, die Auflistung einzelner Aktivitäten und ihrer Eigenschaften sowie die Zwischenspeicherung von Laufzeitmetadaten der Aktivitäten zu einem bestimmten Zeitpunkt. Dieses Thema bietet eine Übersicht über <xref:System.Activities.WorkflowInspectionServices> und die Verwendung zur Überprüfung einer Aktivitätsstruktur.  
  
## <a name="using-workflowinspectionservices"></a>Verwenden von WorkflowInspectionServices  
 Die <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>-Methode wird verwendet, um alle Aktivitäten in der angegebenen Aktivitätsstruktur aufzulisten. <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> gibt ein aufzählbares Element zurück, das alle Aktivitäten in der Struktur umfasst, darunter untergeordnete Elemente, Delegathandler, variable Standardwerte und Argumentausdrücke. Im folgenden Beispiel wird eine Workflowdefinition mithilfe der Elemente <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.WriteLine> und Ausdrücken erstellt. Nachdem die Workflowdefinition erstellt wurde, wird sie aufgerufen. Anschließend wird die `InspectActivity`-Methode aufgerufen.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#45](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#45)]  
  
 Zur Auflistung der Aktivitäten wird <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> für die Stammaktivität und dann erneut rekursiv für jede zurückgegebene Aktivität aufgerufen. Im folgenden Beispiel wird das <xref:System.Activities.Activity.DisplayName%2A>-Objekt von den einzelnen Aktivitäten und Ausdrücken in der Aktivitätsstruktur in die Konsole geschrieben.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#46](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#46)]  
  
 Mit diesem Beispielcode wird die folgende Ausgabe erzeugt.  
  
 **List Item 1**  
**Listenelement 2**
**Listenelement 3**
**Listenelement 4**
**Listenelement 5**
**Artikel, die der Sammlung hinzugefügt wurden.** 
 **Sequenzliterale** **\<<-Listenzeichenfolge>>**  
 **While**  
 **AddToCollection-Zeichenfolge>\<**  
 **VariableValue<\<ICollection String>>**  
 **LambdaValue-Zeichenfolge>\<**  
 **LocationReferenceValue<->>\<**  
 **LambdaValue\<boolesche>**  
 **LocationReferenceValue<->>\<**  
 **ForEach\<String>**  
 **VariableValue<IEnumerable\<String>>**  
 **WriteLine**  
 **DelegateArgumentValue-Zeichenfolge>\<**  
 **Sequenz**  
 **WriteLine**  
 **Literal\<String>** Um eine bestimmte Aktivität abzurufen, anstatt <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> alle Aktivitäten aufzuzählen, wird verwendet. Sowohl mit <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> als auch mit <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> wird die Zwischenspeicherung von Metadaten ausgeführt, wenn `WorkflowInspectionServices.CacheMetadata` zuvor nicht aufgerufen wurde. Wenn <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> aufgerufen wurde, basiert <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> auf den vorhandenen Metadaten. Falls also seit dem letzten Aufruf von <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> Strukturänderungen vorgenommen wurden, kann <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> zu unerwarteten Ergebnissen führen. Wenn nach dem Aufruf <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>Änderungen am Workflow vorgenommen wurden, können <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> Metadaten durch Aufrufen der Methode erneut zwischengespeichert werden. Das Zwischenspeichern von Metadaten wird im nächsten Abschnitt erläutert.  
  
### <a name="caching-metadata"></a>Zwischenspeichern von Metadaten  
 Durch die Zwischenspeicherung der Metadaten für eine Aktivität wird eine Beschreibung der Argumente, Variablen, untergeordneten Aktivitäten und Aktivitätsdelegaten der Aktivität erstellt und validiert. Metadaten werden standardmäßig von der Laufzeit zwischengespeichert, wenn eine Aktivität zur Ausführung vorbereitet wird. Wenn ein Workflowhostautor die Metadaten für eine Aktivität oder eine Aktivitätsstruktur vorher zwischenspeichern möchte, um beispielsweise den gesamten Aufwand im Voraus zu erfassen, kann <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> verwendet werden, um die Metadaten zu dem gewünschten Zeitpunkt zwischenzuspeichern.
