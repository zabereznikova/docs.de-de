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
ms.openlocfilehash: 640a925c3aec86b4743b1b2b62eb3793af1cc0bb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742204"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="973ca-102">CoreResponseData-Klasse</span><span class="sxs-lookup"><span data-stu-id="973ca-102">CoreResponseData Class</span></span>

<span data-ttu-id="973ca-103">Die `CoreResponseData` Klasse stellt das Analysieren der HTTP-Header und den Antworttext.</span><span class="sxs-lookup"><span data-stu-id="973ca-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="973ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="973ca-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="973ca-105">Diese API ist intern, und es ist nicht vorgesehen, direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="973ca-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="973ca-106">Stattdessen sollten Sie verwenden eine <xref:System.Diagnostics.DiagnosticSource> Netzwerk-Code zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="973ca-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="973ca-107">Finden Sie unter [DiagnosticSource-Benutzerhandbuch](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="973ca-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="973ca-108">Microsoft unterstützt nicht die Verwendung dieser Klasse in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="973ca-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="973ca-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="973ca-109">Requirements</span></span>

<span data-ttu-id="973ca-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="973ca-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="973ca-111">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="973ca-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="973ca-112">**.NET Framework-Versionen:** verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="973ca-112">**.NET Framework versions:** Available since 2.0.</span></span>
