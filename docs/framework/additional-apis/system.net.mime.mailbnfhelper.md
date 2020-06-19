---
title: Mailbnfhelper-Klasse (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mime.MailBnfHelper
- System.Net.Mime.MailBnfHelper.Ascii7bitMaxValue
- System.Net.Mime.MailBnfHelper.Atext
- System.Net.Mime.MailBnfHelper.CR
- System.Net.Mime.MailBnfHelper.Ctext
- System.Net.Mime.MailBnfHelper.Dot
- System.Net.Mime.MailBnfHelper.EndComment
- System.Net.Mime.MailBnfHelper.LF
- System.Net.Mime.MailBnfHelper.Space
- System.Net.Mime.MailBnfHelper.StartComment
- System.Net.Mime.MailBnfHelper.Tab
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 86c98726a7886285917b6be8c7631ca1e9e425e6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990450"
---
# <a name="mailbnfhelper-class"></a><span data-ttu-id="3dce4-102">Mailbnfhelper-Klasse</span><span class="sxs-lookup"><span data-stu-id="3dce4-102">MailBnfHelper class</span></span>

<span data-ttu-id="3dce4-103">Enthält Hilfsprogrammmethoden zum Übermitteln von Internet Nachrichten formatierten Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="3dce4-103">Contains utility methods for parsing internet message-formatted strings.</span></span> <span data-ttu-id="3dce4-104">Diese Klasse kann nicht vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="3dce4-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> <span data-ttu-id="3dce4-105">Diese Klasse ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3dce4-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3dce4-106">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="3dce4-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="ascii7bitmaxvalue-field"></a><span data-ttu-id="3dce4-107">Ascii7bitMaxValue-Feld</span><span class="sxs-lookup"><span data-stu-id="3dce4-107">Ascii7bitMaxValue field</span></span>

<span data-ttu-id="3dce4-108">Stellt den maximalen 7-Bit-ASCII-Wert dar.</span><span class="sxs-lookup"><span data-stu-id="3dce4-108">Represents the maximum 7-bit Ascii value.</span></span>

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a><span data-ttu-id="3dce4-109">ATEXT-Feld</span><span class="sxs-lookup"><span data-stu-id="3dce4-109">Atext field</span></span>

<span data-ttu-id="3dce4-110">Stellt die Zeichen dar, die in Atomen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="3dce4-110">Represents the characters allowed in atoms.</span></span>

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a><span data-ttu-id="3dce4-111">CR-Feld</span><span class="sxs-lookup"><span data-stu-id="3dce4-111">CR field</span></span>

<span data-ttu-id="3dce4-112">Stellt das Wagen Rücklauf Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="3dce4-112">Represents the carriage-return character.</span></span>

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a><span data-ttu-id="3dce4-113">CTEXT-Feld</span><span class="sxs-lookup"><span data-stu-id="3dce4-113">Ctext field</span></span>

<span data-ttu-id="3dce4-114">Stellt die Zeichen dar, die innerhalb von Kommentaren zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="3dce4-114">Represents the characters allowed inside of comments.</span></span>

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a><span data-ttu-id="3dce4-115">Punktfeld</span><span class="sxs-lookup"><span data-stu-id="3dce4-115">Dot field</span></span>

<span data-ttu-id="3dce4-116">Stellt das vollendezeichen ( `.` ) dar.</span><span class="sxs-lookup"><span data-stu-id="3dce4-116">Represents the full-stop character (`.`).</span></span>

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a><span data-ttu-id="3dce4-117">EndComment-Feld</span><span class="sxs-lookup"><span data-stu-id="3dce4-117">EndComment field</span></span>

<span data-ttu-id="3dce4-118">Stellt das Zeichen dar, das das Ende eines Kommentars angibt.</span><span class="sxs-lookup"><span data-stu-id="3dce4-118">Represents the character that specifies the end of a comment.</span></span>

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a><span data-ttu-id="3dce4-119">LF-Feld</span><span class="sxs-lookup"><span data-stu-id="3dce4-119">LF field</span></span>

<span data-ttu-id="3dce4-120">Stellt das Zeilenvorschub Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="3dce4-120">Represents the line-feed character.</span></span>

```csharp
internal static readonly char LF
```

## <a name="space-field"></a><span data-ttu-id="3dce4-121">Feld "Space"</span><span class="sxs-lookup"><span data-stu-id="3dce4-121">Space field</span></span>

<span data-ttu-id="3dce4-122">Stellt das Leerzeichen dar.</span><span class="sxs-lookup"><span data-stu-id="3dce4-122">Represents the space character.</span></span>

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a><span data-ttu-id="3dce4-123">StartComment-Feld</span><span class="sxs-lookup"><span data-stu-id="3dce4-123">StartComment field</span></span>

<span data-ttu-id="3dce4-124">Stellt das Zeichen dar, das den Anfang eines Kommentars angibt.</span><span class="sxs-lookup"><span data-stu-id="3dce4-124">Represents the character that specifies the start of a comment.</span></span>

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a><span data-ttu-id="3dce4-125">Registerkarten Feld</span><span class="sxs-lookup"><span data-stu-id="3dce4-125">Tab field</span></span>

<span data-ttu-id="3dce4-126">Stellt das Tabstopp Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="3dce4-126">Represents the tab character.</span></span>

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a><span data-ttu-id="3dce4-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3dce4-127">Requirements</span></span>

<span data-ttu-id="3dce4-128">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="3dce4-128">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="3dce4-129">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="3dce4-129">**Assembly:** System (in System.dll)</span></span>
