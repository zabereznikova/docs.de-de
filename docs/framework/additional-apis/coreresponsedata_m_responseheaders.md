---
title: Coreresponabdata. m_ResponseHeaders-Feld
description: Verstehen Sie das coreresponabdata. m_ResponseHeaders-Feld in .net. Dieses Feld ist ein WebHeaderCollection-Typ, dem Header mit der Serverantwort zugeordnet sind.
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 7c7b896193cb81e9fc9e3ec28110359003a36728
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989795"
---
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="c9fdb-104">Feld "coreresponabdata. m \_ Response Headers"</span><span class="sxs-lookup"><span data-stu-id="c9fdb-104">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="c9fdb-105">`CoreResponseData.m_ResponseHeaders`ist eine <xref:System.Net.WebHeaderCollection> von Headern, die der Serverantwort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-105">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="c9fdb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9fdb-106">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="c9fdb-107">Diese API ist nicht für die direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-107">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="c9fdb-108">Stattdessen sollten Sie einen <xref:System.Diagnostics.DiagnosticSource> zum Anschließen von Netzwerkcode verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-108">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="c9fdb-109">Weitere Informationen finden Sie [im Benutzerhandbuch für diagnosticsource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="c9fdb-109">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="c9fdb-110">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-110">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c9fdb-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c9fdb-111">Requirements</span></span>

<span data-ttu-id="c9fdb-112">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c9fdb-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c9fdb-113">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="c9fdb-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="c9fdb-114">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-114">**.NET Framework versions:** Available since 2.0.</span></span>
