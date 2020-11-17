---
title: Warnung „SYSLIB0001“
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung „SYSLIB0001“ generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: d38d915e902d3c37cc461452f805e8349f11deeb
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439988"
---
# <a name="syslib0001-the-utf-7-encoding-is-insecure"></a>SYSLIB0001: Die UTF-7-Codierung ist unsicher.

Die UTF-7-Codierung wird in Anwendungen kaum noch verwendet, und viele Spezifikationen [verbieten ihre Verwendung](https://security.stackexchange.com/a/68609/3573) im Austausch. Sie wird zuweilen auch in Anwendungen, die keine UTF-7-codierten Daten erwarten, [als Angriffsvektor verwendet](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7). Microsoft warnt vor der Verwendung von <xref:System.Text.UTF7Encoding?displayProperty=nameWithType>, weil es keine Fehlererkennung bereitstellt.

Aufgrund dessen sind die folgenden APIs ab .NET 5.0 als veraltet markiert. Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0001` hervor.

- <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> -Eigenschaft
- <xref:System.Text.UTF7Encoding.%23ctor%2A>-Konstruktoren

## <a name="workarounds"></a>Problemumgehung

- Wenn Sie <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> oder <xref:System.Text.UTF7Encoding> in Ihrem eigenen Protokoll oder Dateiformat verwenden, gehen Sie folgendermaßen vor:

  Wechseln Sie zu <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> oder <xref:System.Text.UTF8Encoding>. UTF-8 ist ein Branchenstandard und wird über Sprachen, Betriebssysteme und Runtimes hinweg flächendeckend unterstützt. Die Verwendung von UTF-8 vereinfacht die zukünftige Wartung Ihres Codes und sorgt für mehr Interoperabilität mit dem Rest des Ökosystems.

- Wenn Sie eine <xref:System.Text.Encoding>-Instanz mit <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> vergleichen, gehen Sie folgendermaßen vor:

  Erwägen Sie stattdessen eine Überprüfung anhand der bekannten UTF-7-Codepage, die `65000` lautet. Durch Vergleichen mit der Codepage vermeiden Sie die Warnung und können außerdem einige Sonderfälle behandeln, wenn beispielsweise jemand `new UTF7Encoding()` aufgerufen oder Unterklassen des Typs erstellt hat.

  ```csharp
  void DoSomething(Encoding enc)
  {
      // Don't perform the check this way.
      // It produces a warning and misses some edge cases.
      if (enc == Encoding.UTF7)
      {
          // Encoding is UTF-7.
      }

      // Instead, perform the check this way.
      if (enc != null && enc.CodePage == 65000)
      {
          // Encoding is UTF-7.
      }
  }
  ```

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Siehe auch

- [UTF-7-Codepfade sind veraltet](3.1-5.0.md#utf-7-code-paths-are-obsolete)
