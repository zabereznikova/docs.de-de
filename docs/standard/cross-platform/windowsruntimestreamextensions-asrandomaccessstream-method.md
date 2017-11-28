---
title: WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
api_name: System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location: System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be93ddc0f3bf0a5079f31bfa0ff5caa882342c37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="63391-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)-Methode</span><span class="sxs-lookup"><span data-stu-id="63391-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>
<span data-ttu-id="63391-103">[Wird nur in .NET Framework 4.5.1 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="63391-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>  
  
 <span data-ttu-id="63391-104">Konvertiert den angegebenen Stream in einen Random-Access-Stream.</span><span class="sxs-lookup"><span data-stu-id="63391-104">Converts the specified stream to a random access stream.</span></span>  
  
 <span data-ttu-id="63391-105">**Namespace:**<xref:System.IO?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="63391-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType></span></span>  
 <span data-ttu-id="63391-106">**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span><span class="sxs-lookup"><span data-stu-id="63391-106">**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63391-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="63391-107">Syntax</span></span>  
  
```csharp  
[CLSCompliantAttribute(false)]  
public static  IRandomAccessStream AsRandomAccessStream(Stream stream)  
```  
  
```vb  
'Declaration  
<ExtensionAttribute> _  
<CLSCompliantAttribute(False)> _  
Public Shared Function AsRandomAccessStream ( _  
        stream As Stream) As IRandomAccessStream  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63391-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="63391-108">Parameters</span></span>  
 `stream`  
  
 <span data-ttu-id="63391-109">Typ: <xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="63391-109">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="63391-110">Der zu konvertierende Stream.</span><span class="sxs-lookup"><span data-stu-id="63391-110">The stream to convert.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63391-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="63391-111">Return Value</span></span>  
 <span data-ttu-id="63391-112">Typ: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span><span class="sxs-lookup"><span data-stu-id="63391-112">Type: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span></span>  
<span data-ttu-id="63391-113">Ein [!INCLUDE[wrt](../../../includes/wrt-md.md)] random-Access-Stream, der den konvertierten Stream darstellt.</span><span class="sxs-lookup"><span data-stu-id="63391-113">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="63391-114">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="63391-114">Exceptions</span></span>  
  
|<span data-ttu-id="63391-115">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="63391-115">Exception</span></span>|<span data-ttu-id="63391-116">Bedingung</span><span class="sxs-lookup"><span data-stu-id="63391-116">Condition</span></span>|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|<span data-ttu-id="63391-117">Der zu konvertierende Stream unterstützt keine Suchvorgänge.</span><span class="sxs-lookup"><span data-stu-id="63391-117">The stream to convert does not support seeking.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63391-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="63391-118">Remarks</span></span>  
 <span data-ttu-id="63391-119">Diese Erweiterungsmethode ist nur verfügbar, wenn Sie Windows Store-Apps entwickeln.</span><span class="sxs-lookup"><span data-stu-id="63391-119">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="63391-120">Diese Methode stellt eine komfortable Möglichkeit des Arbeitens mit Streams in Windows Store-Apps dar.</span><span class="sxs-lookup"><span data-stu-id="63391-120">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="63391-121">Der .NET-Framework, den Sie konvertieren möchten, muss Suchvorgänge unterstützen.</span><span class="sxs-lookup"><span data-stu-id="63391-121">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="63391-122">Weitere Informationen finden Sie unter der Methode <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="63391-122">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="63391-123">Diese API wird in .NET Framework 4.5.1 und neuer, aber nicht in Version 4.5 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63391-123">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>  
  
## <a name="version-information"></a><span data-ttu-id="63391-124">Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="63391-124">Version Information</span></span>  
 <span data-ttu-id="63391-125">**.NET für Windows Store-apps**</span><span class="sxs-lookup"><span data-stu-id="63391-125">**.NET for Windows Store apps**</span></span>  
  
 <span data-ttu-id="63391-126">Unterstützt in: Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="63391-126">Supported in: Windows 8.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63391-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63391-127">See Also</span></span>  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [<span data-ttu-id="63391-128">Gewusst wie: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams</span><span class="sxs-lookup"><span data-stu-id="63391-128">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
