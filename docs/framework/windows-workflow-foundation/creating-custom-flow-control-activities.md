---
title: Erstellen von benutzerdefinierten Flusssteuerungsaktivitäten
ms.date: 03/30/2017
ms.assetid: 27f409f6-2d1d-4cfb-9765-93eb2ad667d5
ms.openlocfilehash: de1378cc0dd304db37aefd437d1ce6feac9f2ed2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724661"
---
# <a name="creating-custom-flow-control-activities"></a>Erstellen von benutzerdefinierten Flusssteuerungsaktivitäten
.NET Framework enthält eine Vielzahl von Flusssteuerungsaktivitäten, die ähnlich wie abstrakte Programmierungsstrukturen (z. B. <xref:System.Activities.Statements.Flowchart>) oder standardmäßige Programmierungsstrukturen (z. B. <xref:System.Activities.Statements.If>) funktionieren. In diesem Thema erläutert die Architektur von einem der Beispielprojekte, [nicht generische ForEach](./samples/non-generic-foreach.md).  
  
## <a name="creating-the-custom-class"></a>Erstellen der benutzerdefinierten Klasse  
 Da die nicht generische ForEach-Klasse untergeordnete Aktivitäten planen muss, muss sie aus <xref:System.Activities.NativeActivity> abgeleitet werden, da aus <xref:System.Workflow.Activities.CodeActivity> abgeleitete Aktivitäten diese Funktion nicht besitzen.  
  
```  
public sealed class ForEach : NativeActivity  
    {  
```  
  
 Die benutzerdefinierte Klasse erfordert mehrere Member, um die von der Aktivität verwendeten Daten zu speichern und die Funktionen zum Ausführen der untergeordneten Aktivitäten der Aktivität bereitzustellen. Folgende Member sind erforderlich:  
  
-   `valueEnumerator`: Die nicht öffentliche <xref:System.Activities.Variable%601> des Typs <xref:System.Collections.IEnumerator> zum Durchlaufen der Auflistung von Elementen verwendet. Dieser Member hat den Typ <xref:System.Activities.Variable%601>, da er intern in der Aktivität verwendet wird. Es handelt sich nicht um ein Argument oder eine öffentliche Eigenschaft, die verwendet werden würden, wenn sich der Ursprung dieses Objekt außerhalb der Aktivität befinden würde.  
  
-   `OnChildComplete`: Die öffentliche <xref:System.Activities.CompletionCallback> -Eigenschaft, die ausgeführt wird, wenn jedes untergeordnete Element die Ausführung abgeschlossen ist. Dieser Member wird als CLR-Eigenschaft definiert, da sein Wert für verschiedene Instanzen der Aktivität unverändert bleibt.  
  
-   `Values`: Die Auflistung von Eingaben, die für die Iterationen der untergeordneten Aktivität verwendet werden soll. Dieser Member hat den Typ <xref:System.Activities.InArgument%601>, da der Ursprung der Daten sich zwar außerhalb der Aktivität befindet, aber der Inhalt der Auflistung während der Ausführung der Aktivität unverändert bleibt. Wenn es für die Aktivität erforderlich ist, den Inhalt dieser Auflistung beim Ausführen der Aktivität zu ändern (um beispielsweise Aktivitäten hinzuzufügen oder zu entfernen), muss dieser Member als <xref:System.Activities.ActivityAction> definiert werden. In diesem Fall findet bei jedem Zugriff eine Auswertung statt, damit Änderungen für die Aktivität zur Verfügung stehen.  
  
-   `Body`: Dieses Element definiert die Aktivität, die für jedes Element ausgeführt werden die `Values` Auflistung. Dieser Member wird als <xref:System.Activities.ActivityAction> definiert, damit bei jedem Zugriff eine Auswertung stattfindet.  
  
-   `Execute`: Diese Methode verwendet die `InternalExecute`, `OnForEachComplete`, und `GetStateAndExecute` nicht öffentliche Member zum Planen der Ausführung und den Abschlusshandler der im textmember definierten untergeordneten Aktivität zuzuweisen.  
  
-   `CacheMetadata`: Dieser Member stellt der Laufzeit mit den Informationen, die sie zum Ausführen der Aktivität benötigt. Standardmäßig informiert die `CacheMetadata`-Methode einer Aktivität die Laufzeit über alle öffentlichen Member der Aktivität. Da diese Aktivität aber für einige Funktionen private Member verwendet, muss die Laufzeit über deren Vorhandensein informiert werden, damit die Laufzeit sie berücksichtigen kann. In diesem Fall wird die `CacheMetadata`-Funktion überschrieben, damit auf den privaten `valueEnumerator`-Member zugegriffen werden kann. Dieser Member erstellt auch ein Argument für die Werte der Aktivität, damit die Werte während der Ausführung an die Aktivität übergeben werden können.
