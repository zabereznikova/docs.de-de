---
title: Bereichsauswahl und Sichtbarkeit der Aktivitätsdefinition
ms.date: 03/30/2017
ms.assetid: ccdffa07-9503-4eea-a61b-17f1564368b7
ms.openlocfilehash: c7f656fee4960a8c43ac58abafba400ed9b35bc1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289164"
---
# <a name="activity-definition-scoping-and-visibility"></a>Bereichsauswahl und Sichtbarkeit der Aktivitätsdefinition

Wie die Bereichsauswahl und Sichtbarkeit eines Objekts beschreibt die Bereichsauswahl und Sichtbarkeit der Aktivitätsdefinition die Fähigkeit anderer Objekte oder Aktivitäten, auf Member der Aktivität zuzugreifen. Die Aktivitätsdefinition erfolgt durch folgende Implementierungen:  
  
1. Bestimmen der Member (<xref:System.Activities.Argument>-, <xref:System.Activities.Variable>- und <xref:System.Activities.ActivityDelegate>-Objekte und untergeordnete Aktivitäten), die den Benutzern von einer Aktivität zur Verfügung gestellt werden.  
  
2. Implementieren der Ausführungslogik der Aktivität  
  
 Die Implementierung umfasst möglicherweise einige Member, die nicht für Consumer der Aktivität bereitgestellt werden, sondern Teil der internen Implementierung sind.  Analog zur Typdefinition ermöglicht das Aktivitätsmodell einem Autor das Qualifizieren der Sichtbarkeit eines Aktivitätsmembers im Hinblick auf die Definition der definierten Aktivität.  Die Sichtbarkeit wirkt sich auf Einzelheiten der Memberverwendung aus, etwa auf Datenbereiche.  
  
## <a name="scope"></a>`Scope`  

 Neben dem Datenbereich kann durch die Sichtbarkeit des Aktivitätsmodells auch der Zugriff auf weitere Aspekte der Aktivität eingeschränkt werden, z. B. Validierung, Debugging, Überwachung oder Nachverfolgung. Ausführungseigenschaften schränken über die Sichtbarkeit und Bereichsauswahl die Ausführungsmerkmale für einen bestimmten Definitionsbereich ein. Sekundäre Stämme schränken über die Sichtbarkeit und Bereichsauswahl den von einer <xref:System.Activities.Statements.CompensableActivity> erfassten Zustand auf den Definitionsbereich ein, in dem kompensierbare Aktivitäten verwendet werden.  
  
## <a name="definition-and-usage"></a>Definition und Verwendung  

 Ein Workflow wird durch das Erstellen neuer Aktivitäten durch die Vererbung von Basis Aktivitäts Klassen und durch die Verwendung von Aktivitäten aus der [integrierten Aktivitäts Bibliothek](net-framework-4-5-built-in-activity-library.md)geschrieben. Damit eine Aktivität verwendet werden kann, muss die Sichtbarkeit der Komponenten ihrer Definition vom Autor der Aktivität konfiguriert werden.  
  
### <a name="activity-members"></a>Aktivitätsmember  

 Das Aktivitätsmodell definiert die Argumente, Variablen, Delegaten und untergeordneten Aktivitäten, die von der Aktivität für Consumer verfügbar gemacht werden. Diese Member können jeweils als `public` oder `private` deklariert werden. Öffentliche Member werden vom Consumer der Aktivität konfiguriert, wohingegen `private`-Member eine Implementierung verwenden, die vom Autor der Aktivität festgelegt wurde. Die Sichtbarkeitsregeln für Datenbereiche lauten wie folgt:  
  
1. Öffentliche Member und die öffentlichen Member von öffentlichen untergeordneten Aktivitäten können auf öffentliche Variablen verweisen.  
  
2. Private Member und die öffentlichen Member von öffentlichen untergeordneten Aktivitäten können auf Argumente und private Variablen verweisen.  
  
 Member, die vom Consumer einer Aktivität festgelegt werden können, sollten niemals privat sein.  
  
### <a name="authoring-models"></a>Erstellungsmodelle  

 Benutzerdefinierte Aktivitäten werden mit <xref:System.Activities.NativeActivity>, <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity> oder <xref:System.Activities.AsyncCodeActivity> definiert. Aktivitäten, die von diesen Klassen abgeleitet werden, können verschiedene Membertypen mit unterschiedlichen Sichtbarkeiten verfügbar machen.  
  
#### <a name="nativeactivity"></a>NativeActivity  

 Aktivitäten, die von <xref:System.Activities.NativeActivity> abgeleitet werden, weisen ein imperatives Codeverhalten auf und können optional mit vorhandenen Aktivitäten definiert werden. Durch Ableiten von Aktivitäten von <xref:System.Activities.NativeActivity> erhalten Sie Zugriff auf alle Funktionen, die von der Laufzeit verfügbar gemacht werden. Alle Member einer entsprechenden Aktivität können mit öffentlicher oder privater Sichtbarkeit definiert werden; eine Ausnahme bilden Argumente, die nur als `public` deklariert werden können.  
  
 Member von Klassen, die von <xref:System.Activities.NativeActivity> abgeleitet werden, werden innerhalb der Laufzeit mit der <xref:System.Activities.NativeActivityMetadata>-Struktur deklariert, die an die <xref:System.Activities.NativeActivity.CacheMetadata%2A>-Methode übergeben wird.  
  
#### <a name="activity"></a>Aktivität  

 Das Verhalten von Aktivitäten, die mit <xref:System.Activities.Activity> erstellt werden, wird ausschließlich durch das Erstellen anderer Aktivitäten definiert. Die <xref:System.Activities.Activity>-Klasse weist eine untergeordnete Implementierungsaktivität auf, die von der Laufzeit mit <xref:System.Activities.Activity.Implementation%2A> abgerufen wird. Aktivitäten, die von <xref:System.Activities.Activity> abgeleitet werden, können öffentliche Argumente, öffentliche Variablen, importierte ActivityDelegates sowie importierte Aktivitäten definieren.  
  
 Importierte ActivityDelegates und Aktivitäten werden als öffentliche untergeordnete Elemente der Aktivität deklariert, können jedoch nicht direkt von der Aktivität geplant werden. Diese Informationen werden während der Validierung verwendet, um die Ausführung von Validierungen für übergeordnete Elemente an Stellen zu vermeiden, an denen die Aktivität niemals ausgeführt wird. Darüber hinaus kann die Implementierung der Aktivität auf importierte untergeordnete Elemente sowie auf öffentliche untergeordnete Elemente verweisen und diese planen. Die Implementierung einer Aktivität, mit der eine Aktivität namens Activity1 importiert wird, kann daher eine <xref:System.Activities.Statements.Sequence> enthalten, mit der Activity1 geplant wird.  
  
#### <a name="codeactivity-asynccodeactivity"></a>CodeActivity/AsyncCodeActivity  

 Diese Basisklasse wird zum Erstellen von Eigenschaften in imperativem Code verwendet. Aktivitäten, die von dieser Klasse abgeleitet werden, können nur auf die Argumente zugreifen, die sie verfügbar machen. Daraus folgt, dass von diesen Aktivitäten nur Member verfügbar gemacht werden können, die öffentliche Argumente darstellen. Andere Member oder Sichtbarkeiten wirken sich nicht auf diese Aktivitäten aus.  
  
#### <a name="summary-of-visibilities"></a>Zusammenfassung der Sichtbarkeiten  

 In der nachstehenden Tabelle werden die Informationen aus den vorangehenden Abschnitten zusammengefasst.  
  
|Memberart|NativeActivity|Aktivität|CodeActivity/AsyncCodeActivity|  
|-----------------|--------------------|--------------|--------------------------------------|  
|Argumente|Öffentlich/Privat|Öffentlich|nicht zutreffend|  
|Variablen|Öffentlich/Privat|Öffentlich|nicht zutreffend|  
|Untergeordnete Aktivitäten|Öffentlich/Privat|Öffentlich, ein privates untergeordnetes Element in der Implementierung festgelegt.|nicht zutreffend|  
|ActivityDelegates|Öffentlich/Privat|Öffentlich|nicht zutreffend|  
  
 Im Allgemeinen sollten Member, die vom Consumer einer Aktivität nicht festgelegt werden können, niemals öffentlich sein.  
  
### <a name="execution-properties"></a>Ausführungseigenschaften  

 In einigen Szenarien ist es hilfreich, den Bereich für eine bestimmte Ausführungseigenschaft auf die öffentlichen untergeordneten Elemente einer Aktivität festzulegen. Die <xref:System.Activities.ExecutionProperties>-Auflistung stellt diese Funktion über die <xref:System.Activities.ExecutionProperties.Add%2A>-Methode bereit. Diese Methode verfügt über einen booleschen Parameter, mit dem angegeben wird, ob eine bestimmte Eigenschaft für alle untergeordneten Elemente oder nur für öffentliche untergeordnete Elemente sichtbar ist. Wenn dieser Parameter auf `true` festgelegt ist, ist die Eigenschaft nur für öffentliche Member sowie für die öffentlichen Member der öffentlichen untergeordneten Elemente sichtbar.  
  
### <a name="secondary-roots"></a>Sekundäre Stämme  

 Ein sekundärer Stamm stellt den internen Mechanismus der Laufzeit zur Verwaltung des Zustands von Kompensationsaktivitäten dar. Wenn die Ausführung einer <xref:System.Activities.Statements.CompensableActivity> abgeschlossen ist, wird der Zustand nicht unmittelbar bereinigt. Stattdessen wird der Zustand von der Laufzeit in einem sekundären Stamm verwaltet, bis der Kompensationsvorgang abgeschlossen ist. Die Speicherortumgebungen, die mit dem sekundären Stamm erfasst werden, entsprechen dem Definitionsbereich, in dem die kompensierbare Aktivität verwendet wird.
