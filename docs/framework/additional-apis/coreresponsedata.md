---
title: CoreResponseData-Klasse
description: Verstehen Sie die coreresponabdata-Klasse, die die Analyse der HTTP-Header und den Antworttext darstellt. Sie befindet sich im System.NET-Namespace in .net.
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 8248cc20f6528a1c3bc64c9b9339a3a3000d03a0
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989799"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="2e76d-104">CoreResponseData-Klasse</span><span class="sxs-lookup"><span data-stu-id="2e76d-104">CoreResponseData Class</span></span>

<span data-ttu-id="2e76d-105">Die `CoreResponseData` -Klasse stellt die Verarbeitung von HTTP-Headern und den Antworttext dar.</span><span class="sxs-lookup"><span data-stu-id="2e76d-105">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e76d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e76d-106">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="2e76d-107">Diese API ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e76d-107">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="2e76d-108">Stattdessen sollten Sie einen <xref:System.Diagnostics.DiagnosticSource> zum Anschließen von Netzwerkcode verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e76d-108">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="2e76d-109">Weitere Informationen finden Sie [im Benutzerhandbuch für diagnosticsource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="2e76d-109">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="2e76d-110">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="2e76d-110">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e76d-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2e76d-111">Requirements</span></span>

<span data-ttu-id="2e76d-112">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="2e76d-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="2e76d-113">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="2e76d-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="2e76d-114">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="2e76d-114">**.NET Framework versions:** Available since 2.0.</span></span>
