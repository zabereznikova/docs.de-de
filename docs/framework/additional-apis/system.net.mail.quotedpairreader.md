---
title: Quotedpaarreader-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.QuotedPairReader
- System.Net.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 9b0bf835a34eecc651894f4336648b73a81b665c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990451"
---
# <a name="quotedpairreader-class"></a><span data-ttu-id="48937-102">Quotedpaarreader-Klasse</span><span class="sxs-lookup"><span data-stu-id="48937-102">QuotedPairReader class</span></span>

<span data-ttu-id="48937-103">Bestimmt, welche Zeichen in einer Zeichenfolge in Anführungszeichen (mit Escapezeichen) angegeben werden</span><span class="sxs-lookup"><span data-stu-id="48937-103">Determines which characters are quoted (escaped) in a quoted string.</span></span> <span data-ttu-id="48937-104">Diese Klasse kann nicht vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="48937-104">This class cannot be inherited.</span></span>

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> <span data-ttu-id="48937-105">Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48937-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="48937-106">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="48937-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="countquotedchars-method"></a><span data-ttu-id="48937-107">Countrytquotedchars-Methode</span><span class="sxs-lookup"><span data-stu-id="48937-107">CountQuotedChars method</span></span>

<span data-ttu-id="48937-108">Zählt die Anzahl der aufeinander folgenden Zeichen in Anführungszeichen, einschließlich mehrerer vorangehender umgekehrter Schrägstriche in der angegebenen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="48937-108">Counts the number of consecutive quoted characters, including multiple preceding quoted backslashes, in the specified string.</span></span> <span data-ttu-id="48937-109">Wenn beispielsweise die Zeichenfolge `a\\\b` und ein Index von angegeben werden `4` , gibt die Methode zurück, da in Anführungszeichen eingeschlossen `4` `b` ist und die drei vorangehenden umgekehrten Schrägstriche sind.</span><span class="sxs-lookup"><span data-stu-id="48937-109">For example, given the string `a\\\b` and an index of `4`, the method returns `4`, because `b` is quoted and so are the three preceding backslashes.</span></span>

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a><span data-ttu-id="48937-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="48937-110">Parameters</span></span>

- <span data-ttu-id="48937-111">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="48937-111">`data` <xref:System.String></span></span>

  <span data-ttu-id="48937-112">Die Daten Zeichenfolge, in der aufeinanderfolgende Anführungszeichen gezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="48937-112">The data string in which to count consecutive quoted characters.</span></span>

- <span data-ttu-id="48937-113">`index` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="48937-113">`index` <xref:System.Int32></span></span>

  <span data-ttu-id="48937-114">Die Position in der angegebenen Zeichenfolge bis zu und einschließlich der aufeinander folgenden Zeichen, die gezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="48937-114">The position in the specified string up to and including which consecutive quoted characters should be counted.</span></span>

- <span data-ttu-id="48937-115">`permitUnicodeEscaping` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="48937-115">`permitUnicodeEscaping` <xref:System.Boolean></span></span>

  <span data-ttu-id="48937-116">`true`, um das Escapezeichen von Unicode-Zeichen zuzulassen. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="48937-116">`true` to permit Unicode characters to be escaped; otherwise, `false`.</span></span>

### <a name="return-value"></a><span data-ttu-id="48937-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="48937-117">Return value</span></span>

<xref:System.Int32?displayProperty=nameWithType>

<span data-ttu-id="48937-118">`0`, wenn das Zeichen am angegebenen Index nicht mit Escapezeichen versehen ist. andernfalls die Anzahl der aufeinander folgenden Zeichen in Anführungszeichen bis einschließlich des Zeichens bei `index` .</span><span class="sxs-lookup"><span data-stu-id="48937-118">`0` if the character at the specified index is not escaped; otherwise, the number of consecutive quoted characters up to and including the character at `index`.</span></span>

### <a name="exceptions"></a><span data-ttu-id="48937-119">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="48937-119">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="48937-120">Ein Escapezeichen mit Escapezeichen wurde gefunden, ist aber nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="48937-120">An escaped Unicode character was found but is not permitted.</span></span>

## <a name="requirements"></a><span data-ttu-id="48937-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="48937-121">Requirements</span></span>

<span data-ttu-id="48937-122">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="48937-122">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="48937-123">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="48937-123">**Assembly:** System (in System.dll)</span></span>
