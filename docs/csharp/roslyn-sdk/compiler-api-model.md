---
title: '.NET Compiler Platform SDK: Konzepte und Objektmodell'
description: In dieser Übersicht erhalten Sie die nötigen Hintergrundinformationen, damit Sie effektiv mit dem .NET Compiler SDK arbeiten können. Erfahren Sie mehr über API-Ebenen, die wichtigsten beteiligten Typen und das gesamte Objektmodell.
ms.date: 07/13/2020
ms.custom: mvc
ms.openlocfilehash: a65d282dd3c58279bbfd635c0386d50ce3f30055
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374467"
---
# <a name="understand-the-net-compiler-platform-sdk-model"></a>Verstehen des .NET Compiler Platform SDK-Modells

Compiler verarbeiten den von Ihnen geschriebenen Code, indem sie sich an strenge Regeln halten, die sich häufig von der Weise unterscheiden, wie Menschen Code lesen und verstehen. Es ist wichtig, dass Sie über grundlegende Kenntnisse zur Funktionsweise des vom Compiler verwendeten Modells verfügen, damit Sie ein Verständnis über die APIs erlangen, die Sie zum Erstellen von Roslyn-basierten Tools verwenden.

## <a name="compiler-pipeline-functional-areas"></a>Funktionsbereiche der Compilerpipeline

Das .NET Compiler Platform SDK stellt Ihnen als Consumer die Codeanalyse des Compilers für C# und Visual Basic zur Verfügung, indem es eine API-Ebene bereitstellt, die eine traditionelle Compilerpipeline nachahmt.

![Schritte der Compilerpipeline, die Quellcode in Objektcode verarbeitet](media/compiler-api-model/compiler-pipeline.png)

Jede Phase dieser Pipeline stellt eine separate Komponente dar. Zunächst wird in der Analysephase Quelltext in Token zerlegt und analysiert, sodass eine Syntax entsteht, die der Grammatik der Sprache entspricht. Dann werden in der Deklarationsphase die Quelle und importierte Metadaten analysiert, sodass sie benannte Symbole formen. In der Bindungsphase werden Bezeichner im Code Symbolen zugeordnet. Zuletzt werden in der Ausgabephase Assemblys mit sämtlichen Informationen ausgegeben, die vom Compiler erstellt wurden.

![Über die API der Compilerpipeline wird Zugriff auf sämtliche Schritte gewährt, die Bestandteil der Compilerpipeline sind.](media/compiler-api-model/compiler-pipeline-api.png)

Für jede dieser Phasen stellt das .NET Compiler Platform SDK ein Objektmodell zur Verfügung, das Zugriff auf die Informationen zu der jeweiligen Phase gewährt. In der Analysephase wird eine Syntaxstruktur zur Verfügung gestellt, in der Deklarationsphase eine hierarchische Symboltabelle und in der Bindungsphase das Ergebnis der semantischen Analyse des Compilers. Die Ausgabephase besteht aus einer API, die IL-Bytecode erstellt.

![Die über die Compiler-API zugänglichen Sprachdienste bei jedem Schritt der Compilerpipeline](media/compiler-api-model/compiler-pipeline-lang-svc.png)

Jeder Compiler vereint diese Komponenten zu einem End-to-End-Objekt.

Bei diesen APIs handelt es sich um dieselben, die von Visual Studio verwendet werden. Beispielsweise verwenden die Features zur Codegliederung und -formatierung die Syntaxstrukturen. Der **Objektkatalog** und die Navigationsfeatures verwenden die Symboltabelle, beim Refactoring und bei **Zu Definition wechseln** wird das Semantikmodell verwendet, und **Bearbeiten und Fortfahren** verwendet all diese Elemente, einschließlich der Ausgabe-API.

## <a name="api-layers"></a>API-Ebenen

Das .NET-Compiler-SDK besteht aus mehreren Ebenen von APIs: Compiler-APIs, Diagnose-APIs, Skript-APIs und Arbeitsbereich-APIs.

### <a name="compiler-apis"></a>Compiler-APIs

Die Compilerebene enthält die Objektmodelle, die mit den Informationen syntaktisch und semantisch übereinstimmen, die in den einzelnen Phasen der Compilerpipeline zur Verfügung gestellt werden. Die Compilerebene enthält außerdem eine nicht veränderbare Momentaufnahme eines einzelnen Aufrufs eines Compilers, einschließlich Assemblyverweisen, Compileroptionen und Quellcodedateien. Es gibt zwei unterschiedliche APIs, die die Sprachen C# und Visual Basic darstellen. Diese beiden APIs verfügen zwar über eine ähnliche Form, sind aber jeweils auf einen hohen Treuegrad in Bezug auf die einzelnen Sprachen ausgelegt. Diese Ebene ist unabhängig von Visual Studio-Komponenten.

### <a name="diagnostic-apis"></a>Diagnose-APIs

Im Rahmen einer Analyse erstellt der Compiler möglicherweise mehrere Diagnosen, die angefangen bei Syntax, Semantik und eindeutigen Zuweisungsfehlern bis hin zu Warnungen und informativen Diagnosen alles abdecken. Die API-Ebene des Compilers stellt über eine erweiterbare API Diagnosen zur Verfügung, über die benutzerdefinierte Analysetools an den Kompilierungsprozess angeschlossen werden. Außerdem können dadurch neben compilerdefinierten Diagnosen benutzerdefinierte Diagnosen erstellt werden, die z.B. von Tools wie StyleCop oder FxCop erstellt werden. Wenn Diagnosen so erstellt werden, hat dies den Vorteil, dass diese auf natürliche Weise in Tools wie MSBuild und Visual Studio integriert werden. Diese Tools sind von Diagnosen abhängig, um z. B. einen Build basierend auf Richtlinien anzuhalten oder Wellenlinien direkt im Editor anzuzeigen und Behebungen für Codefehler vorzuschlagen.

### <a name="scripting-apis"></a>Erstellung von API-Skripts

Das Hosten und Scripting von APIs geschieht auf Compilerebene. Sie können sie verwenden, um Codeausschnitte auszuführen und um Ausführungskontext zur Runtime zu sammeln.
Die interaktive C#-REPL (read–eval–print loop) verwendet diese APIs. Mithilfe der REPL können Sie C# als Skriptsprache verwenden und den Code beim Schreiben interaktiv ausführen.

### <a name="workspaces-apis"></a>Arbeitsbereich-APIs

Die Arbeitsbereich-API ist auf Arbeitsbereichebene enthalten. Sie stellt einen Startpunkt für die Codeanalyse und das Refactoring ganzer Projektmappen dar. Sie unterstützt Sie bei der Aufteilung der Informationen zu den Projekten in einer Projektmappe in einzelne Objektmodelle, gewährt Ihnen direkten Zugriff auf die Objektmodelle auf Compilerebene, ohne dabei Dateien zu analysieren, Optionen zu konfigurieren oder Abhängigkeit zwischen einzelnen Projekten zu verwalten.

Außerdem befinden sich auf Arbeitsbereichsebene mehrere APIs, die bei der Implementierung von Codeanalysen und beim Refactoring von Tools verwendet werden, die in einer Hostumgebung wie der Visual Studio-IDE funktionieren. Nehmen Sie „Alle Verweise suchen“-, „Formatieren“- und Codegenerierungs-APIs als Beispiele.

Diese Ebene ist unabhängig von Visual Studio-Komponenten.
