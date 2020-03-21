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
ms.openlocfilehash: 39a14a3df5059cc47cd4879e4d4ba351cc7b655b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156115"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="c9550-102">CoreResponseData-Klasse</span><span class="sxs-lookup"><span data-stu-id="c9550-102">CoreResponseData Class</span></span>

<span data-ttu-id="c9550-103">Die `CoreResponseData` Klasse stellt die Analyse der HTTP-Header und des Antworttexts dar.</span><span class="sxs-lookup"><span data-stu-id="c9550-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="c9550-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9550-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="c9550-105">Diese API ist intern und soll nicht direkt in Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9550-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="c9550-106">Stattdessen sollten Sie <xref:System.Diagnostics.DiagnosticSource> einen zum Hook-Netzwerkcode verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9550-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="c9550-107">Siehe [DiagnosticSource-Benutzerhandbuch](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="c9550-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="c9550-108">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="c9550-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c9550-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c9550-109">Requirements</span></span>

<span data-ttu-id="c9550-110">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c9550-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c9550-111">**Montage:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="c9550-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="c9550-112">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="c9550-112">**.NET Framework versions:** Available since 2.0.</span></span>
