---
ms.openlocfilehash: a51160a8ab5a4b437e51db31def577f8d8f50182
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065159"
---
### <a name="ca2014-do-not-use-stackalloc-in-loops"></a>CA2014: Verwenden Sie stackalloc nicht in Schleifen.

Die .NET-Codeanalyseregel [CA2014](/visualstudio/code-quality/ca2014) wird ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für jeden C#-Code, in dem ein [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md)-Ausdruck innerhalb einer Schleife verwendet wird.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md). Mehrere dieser Regeln, einschließlich [CA2014](/visualstudio/code-quality/ca2014), werden standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.

Die Regel CA2014 sucht nach C#-Code, in dem ein [stackalloc-Ausdruck](../../../../docs/csharp/language-reference/operators/stackalloc.md) innerhalb einer Schleife verwendet wird. Mit [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) wird Speicher aus dem aktuellen Stapelrahmen belegt. Der Speicher wird erst wieder freigegeben, wenn der aktuelle Methodenaufruf zurückgegeben wird. Dies kann zu Stapelüberläufen führen. Da Ausnahmen von Stapelüberläufen nicht abgefangen werden können, wird die App im Falle eines Stapelüberlaufs beendet.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Aktion

- Verwenden Sie [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) nicht innerhalb von Schleifen. Weisen Sie den Speicherblock außerhalb der Schleife zu, und verwenden Sie ihn innerhalb der Schleife wieder. Weitere Informationen finden Sie unter [CA2014](/visualstudio/code-quality/ca2014).

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Category

Codeanalyse

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
