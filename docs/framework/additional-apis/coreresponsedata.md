---
title: CoreResponseData-Klasse
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
ms.openlocfilehash: fd0ffb982c22b0a8b6cb5dd677faafb9921bf5d9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741019"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="f0baf-102">CoreResponseData-Klasse</span><span class="sxs-lookup"><span data-stu-id="f0baf-102">CoreResponseData Class</span></span>

<span data-ttu-id="f0baf-103">Die `CoreResponseData`-Klasse stellt die Verarbeitung von HTTP-Headern und den Antworttext dar.</span><span class="sxs-lookup"><span data-stu-id="f0baf-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="f0baf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0baf-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="f0baf-105">Diese API ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0baf-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="f0baf-106">Stattdessen sollten Sie einen <xref:System.Diagnostics.DiagnosticSource> zum Anschließen von Netzwerkcode verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0baf-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="f0baf-107">Weitere Informationen finden Sie [im Benutzerhandbuch für diagnosticsource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="f0baf-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="f0baf-108">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="f0baf-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0baf-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0baf-109">Requirements</span></span>

<span data-ttu-id="f0baf-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f0baf-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f0baf-111">**Assembly:** System (in "System. dll")</span><span class="sxs-lookup"><span data-stu-id="f0baf-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f0baf-112">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="f0baf-112">**.NET Framework versions:** Available since 2.0.</span></span>
