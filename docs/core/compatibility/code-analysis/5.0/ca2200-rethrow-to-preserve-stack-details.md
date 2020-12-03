---
title: 'Breaking Change: CA2200: Erneut ausführen, um Stapeldetails beizubehalten.'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, der durch die Aktivierung der Codeanalyseregel „CA2200“ ausgelöst wird.
ms.date: 09/03/2020
ms.openlocfilehash: 74e169906a8b826328de8d4c5f69c32234c2ce95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759472"
---
# <a name="warning-ca2200-rethrow-to-preserve-stack-details"></a>Warnung CA2200: Erneut ausführen, um Stapeldetails beizubehalten.

Die .NET-Codeanalyseregel [CA2200](/visualstudio/code-quality/ca2200) wird ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für alle `catch`-Blöcke, die eine Ausnahme erneut auslösen, und die Ausnahme wird explizit in der `throw`-Anweisung angegeben.

## <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../fundamentals/code-analysis/overview.md). Mehrere dieser Regeln, einschließlich [CA2200](/visualstudio/code-quality/ca2200), sind standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.

Regel CA2200 kennzeichnet Code, bei dem Ausnahmen erneut ausgelöst werden und die Ausnahmevariable in der `throw`-Anweisung angegeben ist. Wenn eine Ausnahme ausgelöst wird, ist ein Teil der darin enthaltenen Informationen die Stapelüberwachung. Die Stapelüberwachung ist eine Liste der Hierarchie der Methodenaufrufe, die mit der Methode beginnt, die die Ausnahme auslöst, und mit der Methode endet, die die Ausnahme abfängt. Wenn eine Ausnahme durch Angabe der Ausnahme in der `throw`-Anweisung erneut ausgelöst wird, startet die Stapelüberwachung bei der aktuellen Methode neu. Die Liste der Methodenaufrufe zwischen der ursprünglichen Methode, die die Ausnahme ausgelöst hat, und der aktuellen Methode geht verloren. Um die ursprünglichen Stapelüberwachungsinformation mit der Ausnahme beizubehalten, verwenden Sie die `throw`-Anweisung ohne Angabe der Ausnahme.

Der folgende Codeausschnitt erzeugt für Regel CA2200 keine Warnung. Die kommentierte Zeile *würde* jedoch einen Verstoß auslösen.

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

- Lösen Sie Ausnahmen erneut aus, ohne die Ausnahme explizit anzugeben. Weitere Informationen finden Sie unter [CA2200](/visualstudio/code-quality/ca2200).

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
