---
ms.openlocfilehash: 00c32c10f77995284264e795d386f699082dcb84
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721770"
---
### <a name="custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively"></a><span data-ttu-id="a9b16-101">Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen</span><span class="sxs-lookup"><span data-stu-id="a9b16-101">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>

<span data-ttu-id="a9b16-102">Benutzerdefinierte <xref:System.Text.EncoderFallbackBuffer>-Instanzen können kein rekursives Fallback ausführen.</span><span class="sxs-lookup"><span data-stu-id="a9b16-102">Custom <xref:System.Text.EncoderFallbackBuffer> instances cannot fall back recursively.</span></span> <span data-ttu-id="a9b16-103">Die Implementierung von <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> muss zu einer Zeichensequenz führen, die in die Zielcodierung konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a9b16-103">The implementation of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must result in a character sequence that is convertible to the destination encoding.</span></span> <span data-ttu-id="a9b16-104">Andernfalls tritt eine Ausnahme auf.</span><span class="sxs-lookup"><span data-stu-id="a9b16-104">Otherwise, an exception occurs.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a9b16-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a9b16-105">Change description</span></span>

<span data-ttu-id="a9b16-106">Bei einem Zeichen-zu-Byte-Transcodierungsvorgang erkennt die Runtime falsch formatierte oder nicht konvertierbare UTF-16-Sequenzen und stellt diese Zeichen für die <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>-Methode bereit.</span><span class="sxs-lookup"><span data-stu-id="a9b16-106">During a character-to-byte transcoding operation, the runtime detects ill-formed or nonconvertible UTF-16 sequences and provides those characters to the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a9b16-107">Die `Fallback`-Methode bestimmt, welche Zeichen die ursprünglichen nicht konvertierbaren Daten ersetzen, und diese Zeichen werden durch Aufrufen von <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in einer Schleife ausgeglichen.</span><span class="sxs-lookup"><span data-stu-id="a9b16-107">The `Fallback` method determines which characters should be substituted for the original nonconvertible data, and these characters are drained by calling <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in a loop.</span></span>

<span data-ttu-id="a9b16-108">Die Runtime versucht dann, diese Ersetzungszeichen in die Zielcodierung zu transcodieren.</span><span class="sxs-lookup"><span data-stu-id="a9b16-108">The runtime then attempts to transcode these substitution characters to the target encoding.</span></span> <span data-ttu-id="a9b16-109">Wenn dieser Vorgang erfolgreich ist, setzt die Runtime die Transcodierung an der Stelle fort, an der sie die ursprüngliche Eingabezeichenfolge verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="a9b16-109">If this operation succeeds, the runtime continues transcoding from where it left off in the original input string.</span></span>

<span data-ttu-id="a9b16-110">In .NET Core Vorschau 7 und früheren Versionen können von benutzerdefinierten Implementierungen von <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> Zeichensequenzen zurückgegeben werden, die nicht in die Zielcodierung konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="a9b16-110">In .NET Core Preview 7 and earlier versions, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> can return character sequences that are not convertible to the destination encoding.</span></span> <span data-ttu-id="a9b16-111">Wenn die ersetzten Zeichen nicht in die Zielcodierung transcodiert werden können, ruft die Runtime die <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>-Methode erneut mit den Ersetzungszeichen auf, wobei erwartet wird, dass die <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>-Methode eine neue Ersetzungssequenz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a9b16-111">If the substituted characters cannot be transcoded to the target encoding, the runtime invokes the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method once again with the substitution characters, expecting the <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> method to return a new substitution sequence.</span></span> <span data-ttu-id="a9b16-112">Dieser Vorgang wird fortgesetzt, bis die Laufzeit eine wohlgeformte, konvertierbare Ersetzung erkennt oder eine maximale Anzahl von Rekursionen erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="a9b16-112">This process continues until the runtime eventually sees a well-formed, convertible substitution, or until a maximum recursion count is reached.</span></span>

<span data-ttu-id="a9b16-113">Ab .NET Core 3.0 müssen von benutzerdefinierten Implementierungen von <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> Zeichensequenzen zurückgegeben werden, die in die Zielcodierung konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="a9b16-113">Starting with .NET Core 3.0, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must return character sequences that are convertible to the destination encoding.</span></span> <span data-ttu-id="a9b16-114">Wenn die ersetzten Zeichen nicht in die Zielcodierung transcodiert werden können, wird eine <xref:System.ArgumentException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a9b16-114">If the substituted characters cannot be transcoded to the target encoding, an <xref:System.ArgumentException> is thrown.</span></span> <span data-ttu-id="a9b16-115">Die Laufzeit führt keine rekursiven Aufrufe der <xref:System.Text.EncoderFallbackBuffer>-Instanz mehr durch.</span><span class="sxs-lookup"><span data-stu-id="a9b16-115">The runtime will no longer make recursive calls into the <xref:System.Text.EncoderFallbackBuffer> instance.</span></span>

<span data-ttu-id="a9b16-116">Dieses Verhalten gilt nur, wenn alle drei der folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="a9b16-116">This behavior only applies when all three of the following conditions are met:</span></span>

- <span data-ttu-id="a9b16-117">Die Runtime erkennt eine falsch formatierte UTF-16-Sequenz oder eine UTF-16-Sequenz, die nicht in die Zielcodierung konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a9b16-117">The runtime detects an ill-formed UTF-16 sequence or a UTF-16 sequence that cannot be converted to the target encoding.</span></span>
- <span data-ttu-id="a9b16-118">Ein benutzerdefinierter <xref:System.Text.EncoderFallback> wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="a9b16-118">A custom <xref:System.Text.EncoderFallback> has been specified.</span></span>
- <span data-ttu-id="a9b16-119">Der benutzerdefinierte <xref:System.Text.EncoderFallback> versucht, eine neue falsch formatierte oder nicht konvertierbare UTF-16-Sequenz zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="a9b16-119">The custom <xref:System.Text.EncoderFallback> attempts to substitute a new ill-formed or nonconvertible UTF-16 sequence.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a9b16-120">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a9b16-120">Version introduced</span></span>

<span data-ttu-id="a9b16-121">3.0</span><span class="sxs-lookup"><span data-stu-id="a9b16-121">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a9b16-122">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="a9b16-122">Recommended action</span></span>

<span data-ttu-id="a9b16-123">Die meisten Entwickler müssen keine Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="a9b16-123">Most developers needn't take any action.</span></span>

<span data-ttu-id="a9b16-124">Wenn eine Anwendung eine benutzerdefinierte <xref:System.Text.EncoderFallback>- und <xref:System.Text.EncoderFallbackBuffer>-Klasse verwendet, stellen Sie sicher, dass die Implementierung von <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> den Fallbackpuffer mit wohlgeformten UTF-16-Daten auffüllt, die direkt in die Zielcodierung konvertiert werden können, wenn die <xref:System.Text.EncoderFallbackBuffer.Fallback%2A>-Methode zuerst von der Runtime aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a9b16-124">If an application uses a custom <xref:System.Text.EncoderFallback> and <xref:System.Text.EncoderFallbackBuffer> class, ensure the implementation of <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> populates the fallback buffer with well-formed UTF-16 data that is directly convertible to the target encoding when the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> method is first invoked by the runtime.</span></span>

#### <a name="category"></a><span data-ttu-id="a9b16-125">Kategorie</span><span class="sxs-lookup"><span data-stu-id="a9b16-125">Category</span></span>

<span data-ttu-id="a9b16-126">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="a9b16-126">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a9b16-127">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a9b16-127">Affected APIs</span></span>

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>
- <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.EncoderFallbackBuffer.Fallback`
- `M:System.Text.EncoderFallbackBuffer.GetNextChar`

-->
