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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675415"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="f5f73-102">CoreResponseData-Klasse</span><span class="sxs-lookup"><span data-stu-id="f5f73-102">CoreResponseData Class</span></span>

<span data-ttu-id="f5f73-103">Die `CoreResponseData` Klasse stellt das Analysieren der HTTP-Header und Text der Antwort.</span><span class="sxs-lookup"><span data-stu-id="f5f73-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="f5f73-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5f73-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="f5f73-105">Diese API ist intern, und sie ist nicht vorgesehen, direkt in Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5f73-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="f5f73-106">Sie sollten stattdessen eine <xref:System.Diagnostics.DiagnosticSource> Netzwerk-Code zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="f5f73-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="f5f73-107">Finden Sie unter [DiagnosticSource-Benutzerhandbuch](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="f5f73-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="f5f73-108">Microsoft unterstützt nicht die Verwendung dieser Klasse in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="f5f73-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f5f73-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5f73-109">Requirements</span></span>

<span data-ttu-id="f5f73-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f5f73-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f5f73-111">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="f5f73-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f5f73-112">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="f5f73-112">**.NET Framework versions:** Available since 2.0.</span></span>
