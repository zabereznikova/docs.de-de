---
title: Warnung „SYSLIB0001“
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung „SYSLIB0001“ generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: d275717e22b260d9ceff4fe94993e9a0e6996cf0
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437837"
---
# <a name="syslib0001-the-utf-7-encoding-is-insecure"></a><span data-ttu-id="d020c-103">SYSLIB0001: Die UTF-7-Codierung ist unsicher.</span><span class="sxs-lookup"><span data-stu-id="d020c-103">SYSLIB0001: The UTF-7 encoding is insecure</span></span>

<span data-ttu-id="d020c-104">Die UTF-7-Codierung wird in Anwendungen kaum noch verwendet, und viele Spezifikationen [verbieten ihre Verwendung](https://security.stackexchange.com/a/68609/3573) im Austausch.</span><span class="sxs-lookup"><span data-stu-id="d020c-104">The UTF-7 encoding is no longer in wide use among applications, and many specs now [forbid its use](https://security.stackexchange.com/a/68609/3573) in interchange.</span></span> <span data-ttu-id="d020c-105">Sie wird zuweilen auch in Anwendungen, die keine UTF-7-codierten Daten erwarten, [als Angriffsvektor verwendet](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7).</span><span class="sxs-lookup"><span data-stu-id="d020c-105">It's also occasionally [used as an attack vector](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) in applications that don't anticipate encountering UTF-7-encoded data.</span></span> <span data-ttu-id="d020c-106">Microsoft warnt vor der Verwendung von <xref:System.Text.UTF7Encoding?displayProperty=nameWithType>, weil es keine Fehlererkennung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d020c-106">Microsoft warns against use of <xref:System.Text.UTF7Encoding?displayProperty=nameWithType> because it doesn't provide error detection.</span></span>

<span data-ttu-id="d020c-107">Aufgrund dessen sind die folgenden APIs ab .NET 5.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d020c-107">Consequently, the following APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="d020c-108">Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0001` hervor.</span><span class="sxs-lookup"><span data-stu-id="d020c-108">Use of these APIs generates warning `SYSLIB0001` at compile time.</span></span>

- <span data-ttu-id="d020c-109"><xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d020c-109"><xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> property</span></span>
- <span data-ttu-id="d020c-110"><xref:System.Text.UTF7Encoding.%23ctor%2A>-Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="d020c-110"><xref:System.Text.UTF7Encoding.%23ctor%2A> constructors</span></span>

## <a name="workarounds"></a><span data-ttu-id="d020c-111">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="d020c-111">Workarounds</span></span>

- <span data-ttu-id="d020c-112">Wenn Sie <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> oder <xref:System.Text.UTF7Encoding> in Ihrem eigenen Protokoll oder Dateiformat verwenden, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="d020c-112">If you're using <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> or <xref:System.Text.UTF7Encoding> within your own protocol or file format:</span></span>

  <span data-ttu-id="d020c-113">Wechseln Sie zu <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> oder <xref:System.Text.UTF8Encoding>.</span><span class="sxs-lookup"><span data-stu-id="d020c-113">Switch to using <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> or <xref:System.Text.UTF8Encoding>.</span></span> <span data-ttu-id="d020c-114">UTF-8 ist ein Branchenstandard und wird über Sprachen, Betriebssysteme und Runtimes hinweg flächendeckend unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d020c-114">UTF-8 is an industry standard and is widely supported across languages, operating systems, and runtimes.</span></span> <span data-ttu-id="d020c-115">Die Verwendung von UTF-8 vereinfacht die zukünftige Wartung Ihres Codes und sorgt für mehr Interoperabilität mit dem Rest des Ökosystems.</span><span class="sxs-lookup"><span data-stu-id="d020c-115">Using UTF-8 eases future maintenance of your code and makes it more interoperable with the rest of the ecosystem.</span></span>

- <span data-ttu-id="d020c-116">Wenn Sie eine <xref:System.Text.Encoding>-Instanz mit <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> vergleichen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="d020c-116">If you're comparing an <xref:System.Text.Encoding> instance against <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>:</span></span>

  <span data-ttu-id="d020c-117">Erwägen Sie stattdessen eine Überprüfung anhand der bekannten UTF-7-Codepage, die `65000` lautet.</span><span class="sxs-lookup"><span data-stu-id="d020c-117">Instead, consider performing a check against the well-known UTF-7 code page, which is `65000`.</span></span> <span data-ttu-id="d020c-118">Durch Vergleichen mit der Codepage vermeiden Sie die Warnung und können außerdem einige Sonderfälle behandeln, wenn beispielsweise jemand `new UTF7Encoding()` aufgerufen oder Unterklassen des Typs erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="d020c-118">By comparing against the code page, you avoid the warning and also handle some edge cases, such as if somebody called `new UTF7Encoding()` or subclassed the type.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d020c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d020c-119">See also</span></span>

- [<span data-ttu-id="d020c-120">UTF-7-Codepfade sind veraltet</span><span class="sxs-lookup"><span data-stu-id="d020c-120">UTF-7 code paths are obsolete</span></span>](core-libraries/5.0/utf-7-code-paths-obsolete.md)
