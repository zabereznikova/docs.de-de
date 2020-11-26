---
title: Erstellen von benutzerdefinierten Flusssteuerungsaktivitäten
ms.date: 03/30/2017
ms.assetid: 27f409f6-2d1d-4cfb-9765-93eb2ad667d5
ms.openlocfilehash: 92d98d33b10e431248c4c482fcd26f3036c4c330
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242070"
---
# <a name="creating-custom-flow-control-activities"></a>Erstellen von benutzerdefinierten Flusssteuerungsaktivitäten

Die .NET Framework enthält eine Reihe von Fluss Steuerungsaktivitäten, die ähnlich wie abstrakte Programmierstrukturen (z. b. <xref:System.Activities.Statements.Flowchart> ) oder Standard Programmierungs Anweisungen (z <xref:System.Activities.Statements.If> . b.) funktionieren. In diesem Thema wird die Architektur eines der Beispiel Projekte erläutert, [nicht generisch foreach](./samples/non-generic-foreach.md).  
  
## <a name="creating-the-custom-class"></a>Erstellen der benutzerdefinierten Klasse  

 Da die nicht generische ForEach-Klasse untergeordnete Aktivitäten planen muss, muss sie aus <xref:System.Activities.NativeActivity> abgeleitet werden, da aus <xref:System.Workflow.Activities.CodeActivity> abgeleitete Aktivitäten diese Funktion nicht besitzen.  
  
```csharp  
public sealed class ForEach : NativeActivity  
{
}
```  
  
 Die benutzerdefinierte Klasse erfordert mehrere Member, um die von der Aktivität verwendeten Daten zu speichern und die Funktionen zum Ausführen der untergeordneten Aktivitäten der Aktivität bereitzustellen. Folgende Member sind erforderlich:  
  
- `valueEnumerator`: Die nicht öffentliche <xref:System.Activities.Variable%601> vom Typ <xref:System.Collections.IEnumerator>, die verwendet wird, um die Auflistung von Elementen zu durchlaufen. Dieser Member hat den Typ <xref:System.Activities.Variable%601>, da er intern in der Aktivität verwendet wird. Es handelt sich nicht um ein Argument oder eine öffentliche Eigenschaft, die verwendet werden würden, wenn sich der Ursprung dieses Objekt außerhalb der Aktivität befinden würde.  
  
- `OnChildComplete`: Die öffentliche <xref:System.Activities.CompletionCallback>-Eigenschaft, die ausgeführt wird, wenn jedes untergeordnete Element die Ausführung abschließt. Dieser Member wird als CLR-Eigenschaft definiert, da sein Wert für verschiedene Instanzen der Aktivität unverändert bleibt.  
  
- `Values`: Die Auflistung von Eingaben, die für die Iterationen der untergeordneten Aktivität verwendet wird. Dieser Member hat den Typ <xref:System.Activities.InArgument%601>, da der Ursprung der Daten sich zwar außerhalb der Aktivität befindet, aber der Inhalt der Auflistung während der Ausführung der Aktivität unverändert bleibt. Wenn es für die Aktivität erforderlich ist, den Inhalt dieser Auflistung beim Ausführen der Aktivität zu ändern (um beispielsweise Aktivitäten hinzuzufügen oder zu entfernen), muss dieser Member als <xref:System.Activities.ActivityAction> definiert werden. In diesem Fall findet bei jedem Zugriff eine Auswertung statt, damit Änderungen für die Aktivität zur Verfügung stehen.  
  
- `Body`: Dieser Member definiert die Aktivität, die für jedes Element in der `Values`-Auflistung ausgeführt werden soll. Dieser Member wird als <xref:System.Activities.ActivityAction> definiert, damit bei jedem Zugriff eine Auswertung stattfindet.  
  
- `Execute`: Diese Methode verwendet die nicht öffentlichen Member `InternalExecute`, `OnForEachComplete` und `GetStateAndExecute`, um die Ausführung zu planen und den Abschlusshandler der im Textmember definierten untergeordneten Aktivität zuzuweisen.  
  
- `CacheMetadata`: Dieser Member stellt der Laufzeit die Informationen bereit, die zum Ausführen der Aktivität erforderlich sind. Standardmäßig informiert die `CacheMetadata`-Methode einer Aktivität die Laufzeit über alle öffentlichen Member der Aktivität. Da diese Aktivität aber für einige Funktionen private Member verwendet, muss die Laufzeit über deren Vorhandensein informiert werden, damit die Laufzeit sie berücksichtigen kann. In diesem Fall wird die `CacheMetadata`-Funktion überschrieben, damit auf den privaten `valueEnumerator`-Member zugegriffen werden kann. Dieser Member erstellt auch ein Argument für die Werte der Aktivität, damit die Werte während der Ausführung an die Aktivität übergeben werden können.
