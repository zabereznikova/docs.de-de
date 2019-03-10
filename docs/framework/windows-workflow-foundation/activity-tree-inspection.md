---
title: Aktivitätsstrukturüberprüfung
ms.date: 03/30/2017
ms.assetid: 100d00e4-8c1d-4233-8fbb-dd443a01155d
ms.openlocfilehash: 014795b79b3536b387096e4de64266e26649da21
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705492"
---
# <a name="activity-tree-inspection"></a>Aktivitätsstrukturüberprüfung
Die Aktivitätsstrukturüberprüfung wird von Workflowanwendungsautoren verwendet, um die von der Anwendung gehosteten Workflows zu überprüfen. <xref:System.Activities.WorkflowInspectionServices> ermöglicht die Suche nach bestimmten untergeordneten Aktivitäten in Workflows, die Auflistung einzelner Aktivitäten und ihrer Eigenschaften sowie die Zwischenspeicherung von Laufzeitmetadaten der Aktivitäten zu einem bestimmten Zeitpunkt. Dieses Thema bietet eine Übersicht über <xref:System.Activities.WorkflowInspectionServices> und die Verwendung zur Überprüfung einer Aktivitätsstruktur.  
  
## <a name="using-workflowinspectionservices"></a>Verwenden von WorkflowInspectionServices  
 Die <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>-Methode wird verwendet, um alle Aktivitäten in der angegebenen Aktivitätsstruktur aufzulisten. <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> gibt ein aufzählbares Element zurück, das alle Aktivitäten in der Struktur umfasst, darunter untergeordnete Elemente, Delegathandler, variable Standardwerte und Argumentausdrücke. Im folgenden Beispiel wird eine Workflowdefinition mithilfe der Elemente <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.WriteLine> und Ausdrücken erstellt. Nachdem die Workflowdefinition erstellt wurde, wird sie aufgerufen. Anschließend wird die `InspectActivity`-Methode aufgerufen.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#45](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#45)]  
  
 Zur Auflistung der Aktivitäten wird <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> für die Stammaktivität und dann erneut rekursiv für jede zurückgegebene Aktivität aufgerufen. Im folgenden Beispiel wird das <xref:System.Activities.Activity.DisplayName%2A>-Objekt von den einzelnen Aktivitäten und Ausdrücken in der Aktivitätsstruktur in die Konsole geschrieben.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#46](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#46)]  
  
 Mit diesem Beispielcode wird die folgende Ausgabe erzeugt.  
  
 **Listenelement 1**  
**Auflisten von Element 2**   
**Auflisten von Element 3**   
**Auflisten von Element 4**   
**Listenelement 5**   
**Elemente, die zur Auflistung hinzugefügt werden.**   
**Sequenz**   
 **Literal < Liste\<Zeichenfolge >>**  
 **While**  
 **AddToCollection\<String>**  
 **VariableValue < ICollection\<Zeichenfolge >>**  
 **LambdaValue\<String>**  
 **LocationReferenceValue<List\<String>>**  
 **LambdaValue\<Boolean>**  
 **LocationReferenceValue<List\<String>>**  
 **ForEach\<String>**  
 **VariableValue < IEnumerable\<Zeichenfolge >>**  
 **WriteLine**  
 **DelegateArgumentValue\<String>**  
 **Sequence**  
 **WriteLine**  
 **Literal\<Zeichenfolge >** zum Abrufen einer bestimmten Aktivität anstelle Auflisten aller Aktivitäten <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> verwendet wird. Sowohl mit <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> als auch mit <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> wird die Zwischenspeicherung von Metadaten ausgeführt, wenn `WorkflowInspectionServices.CacheMetadata` zuvor nicht aufgerufen wurde. Wenn <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> aufgerufen wurde, basiert <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> auf den vorhandenen Metadaten. Falls also seit dem letzten Aufruf von <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> Strukturänderungen vorgenommen wurden, kann <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> zu unerwarteten Ergebnissen führen. Wenn Sie Änderungen an den Workflow nach dem Aufruf vorgenommen wurden <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>, Metadaten kann zwischengespeichert werden, erneut durch Aufrufen der <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> Methode. Das Zwischenspeichern von Metadaten wird im nächsten Abschnitt erläutert.  
  
### <a name="caching-metadata"></a>Zwischenspeichern von Metadaten  
 Durch die Zwischenspeicherung der Metadaten für eine Aktivität wird eine Beschreibung der Argumente, Variablen, untergeordneten Aktivitäten und Aktivitätsdelegaten der Aktivität erstellt und validiert. Metadaten werden standardmäßig von der Laufzeit zwischengespeichert, wenn eine Aktivität zur Ausführung vorbereitet wird. Wenn ein Workflowhostautor die Metadaten für eine Aktivität oder eine Aktivitätsstruktur vorher zwischenspeichern möchte, um beispielsweise den gesamten Aufwand im Voraus zu erfassen, kann <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> verwendet werden, um die Metadaten zu dem gewünschten Zeitpunkt zwischenzuspeichern.
