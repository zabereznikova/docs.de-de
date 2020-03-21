---
title: CoreResponseData.m_ResponseHeaders-Feld
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
ms.openlocfilehash: 723df6dc2de978695608d106e3a01bde286fc4fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156102"
---
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="4e465-102">CoreResponseData.m\_ResponseHeaders-Feld</span><span class="sxs-lookup"><span data-stu-id="4e465-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="4e465-103">`CoreResponseData.m_ResponseHeaders`ist <xref:System.Net.WebHeaderCollection> ein Header, der der Serverantwort zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4e465-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e465-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e465-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="4e465-105">Diese API ist nicht dazu gedacht, direkt in Ihrem Code verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="4e465-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="4e465-106">Stattdessen sollten Sie <xref:System.Diagnostics.DiagnosticSource> einen zum Hook-Netzwerkcode verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e465-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="4e465-107">Siehe [DiagnosticSource-Benutzerhandbuch](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="4e465-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="4e465-108">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="4e465-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4e465-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4e465-109">Requirements</span></span>

<span data-ttu-id="4e465-110">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="4e465-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="4e465-111">**Montage:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="4e465-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="4e465-112">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="4e465-112">**.NET Framework versions:** Available since 2.0.</span></span>
