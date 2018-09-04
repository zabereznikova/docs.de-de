---
title: WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)-Methode
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
api_name:
- System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location:
- System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a712414163446606cbc93154bc821d3b1166fe8f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561795"
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="c3dc7-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)-Methode</span><span class="sxs-lookup"><span data-stu-id="c3dc7-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>

<span data-ttu-id="c3dc7-103">[Wird nur in .NET Framework 4.5.1 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="c3dc7-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>

<span data-ttu-id="c3dc7-104">Konvertiert den angegebenen Stream in einen Random-Access-Stream.</span><span class="sxs-lookup"><span data-stu-id="c3dc7-104">Converts the specified stream to a random access stream.</span></span>

<span data-ttu-id="c3dc7-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType> 
 **Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span><span class="sxs-lookup"><span data-stu-id="c3dc7-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType>
**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>

## <a name="syntax"></a><span data-ttu-id="c3dc7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3dc7-106">Syntax</span></span>

```csharp
[CLSCompliantAttribute(false)]
public static IRandomAccessStream AsRandomAccessStream(Stream stream)
```

```vb
'Declaration
<ExtensionAttribute> _
<CLSCompliantAttribute(False)> _
Public Shared Function AsRandomAccessStream ( _
        stream As Stream) As IRandomAccessStream
```

## <a name="parameters"></a><span data-ttu-id="c3dc7-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="c3dc7-107">Parameters</span></span>

`stream`

<span data-ttu-id="c3dc7-108">Typ: <xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c3dc7-108">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="c3dc7-109">Der zu konvertierende Stream.</span><span class="sxs-lookup"><span data-stu-id="c3dc7-109">The stream to convert.</span></span>

## <a name="return-value"></a><span data-ttu-id="c3dc7-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c3dc7-110">Return Value</span></span>

<span data-ttu-id="c3dc7-111">Typ: <xref:Windows.Storage.Streams.RandomAccessStream></span><span class="sxs-lookup"><span data-stu-id="c3dc7-111">Type: <xref:Windows.Storage.Streams.RandomAccessStream></span></span>  
<span data-ttu-id="c3dc7-112">Ein [!INCLUDE[wrt](../../../includes/wrt-md.md)] random Access-Stream, der den konvertierten Stream darstellt.</span><span class="sxs-lookup"><span data-stu-id="c3dc7-112">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>

## <a name="exceptions"></a><span data-ttu-id="c3dc7-113">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="c3dc7-113">Exceptions</span></span>

|<span data-ttu-id="c3dc7-114">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="c3dc7-114">Exception</span></span>|<span data-ttu-id="c3dc7-115">Bedingung</span><span class="sxs-lookup"><span data-stu-id="c3dc7-115">Condition</span></span>|
|---------------|---------------|
|<xref:System.NotSupportedException>|<span data-ttu-id="c3dc7-116">Der zu konvertierende Stream unterstützt keine Suchvorgänge.</span><span class="sxs-lookup"><span data-stu-id="c3dc7-116">The stream to convert does not support seeking.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c3dc7-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3dc7-117">Remarks</span></span>

<span data-ttu-id="c3dc7-118">Diese Erweiterungsmethode ist nur verfügbar, wenn Sie Windows Store-Apps entwickeln.</span><span class="sxs-lookup"><span data-stu-id="c3dc7-118">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="c3dc7-119">Diese Methode stellt eine komfortable Möglichkeit des Arbeitens mit Streams in Windows Store-Apps dar.</span><span class="sxs-lookup"><span data-stu-id="c3dc7-119">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="c3dc7-120">Der .NET-Framework, den Sie konvertieren möchten, muss Suchvorgänge unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c3dc7-120">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="c3dc7-121">Weitere Informationen finden Sie unter der Methode <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c3dc7-121">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3dc7-122">Diese API wird in .NET Framework 4.5.1 und neuer, aber nicht in Version 4.5 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c3dc7-122">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>

## <a name="version-information"></a><span data-ttu-id="c3dc7-123">Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="c3dc7-123">Version Information</span></span>

<span data-ttu-id="c3dc7-124">**.NET für Windows Store-apps**</span><span class="sxs-lookup"><span data-stu-id="c3dc7-124">**.NET for Windows Store apps**</span></span>

<span data-ttu-id="c3dc7-125">Unterstützt in: Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c3dc7-125">Supported in: Windows 8.1</span></span>

## <a name="see-also"></a><span data-ttu-id="c3dc7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3dc7-126">See Also</span></span>

<span data-ttu-id="c3dc7-127">[System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions(v=vs.110).aspx)</span><span class="sxs-lookup"><span data-stu-id="c3dc7-127">[System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions(v=vs.110).aspx)</span></span>  
[<span data-ttu-id="c3dc7-128">Gewusst wie: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams</span><span class="sxs-lookup"><span data-stu-id="c3dc7-128">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  