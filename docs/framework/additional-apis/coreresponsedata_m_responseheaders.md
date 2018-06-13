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
ms.openlocfilehash: ea93b70ae8e1a710b4208050d7ec823a28b218b7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753663"
---
# <a name="coreresponsedatamresponseheaders-field"></a><span data-ttu-id="97368-102">CoreResponseData.m\_ResponseHeaders-Feld</span><span class="sxs-lookup"><span data-stu-id="97368-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="97368-103">`CoreResponseData.m_ResponseHeaders` ist eine <xref:System.Net.WebHeaderCollection> von Headern, die die Antwort des Servers zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="97368-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="97368-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97368-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="97368-105">Diese API ist nicht vorgesehen, direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="97368-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="97368-106">Stattdessen sollten Sie verwenden eine <xref:System.Diagnostics.DiagnosticSource> Netzwerk-Code zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="97368-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="97368-107">Finden Sie unter [DiagnosticSource-Benutzerhandbuch](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="97368-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="97368-108">Microsoft unterstützt nicht die Verwendung dieser Klasse in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="97368-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="97368-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97368-109">Requirements</span></span>

<span data-ttu-id="97368-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="97368-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="97368-111">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="97368-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="97368-112">**.NET Framework-Versionen:** verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="97368-112">**.NET Framework versions:** Available since 2.0.</span></span>
