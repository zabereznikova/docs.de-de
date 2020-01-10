---
title: Coreresponabdata. m_ResponseHeaders-Feld
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
ms.openlocfilehash: df0b592a5f85d4c99dee4ecb60963f4abb560a13
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741007"
---
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="2166b-102">Coreresponabdata. m\_Response Headers-Feld</span><span class="sxs-lookup"><span data-stu-id="2166b-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="2166b-103">`CoreResponseData.m_ResponseHeaders` ist eine <xref:System.Net.WebHeaderCollection> von Headern, die der Serverantwort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2166b-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="2166b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2166b-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="2166b-105">Diese API ist nicht für die direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="2166b-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="2166b-106">Stattdessen sollten Sie einen <xref:System.Diagnostics.DiagnosticSource> zum Anschließen von Netzwerkcode verwenden.</span><span class="sxs-lookup"><span data-stu-id="2166b-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="2166b-107">Weitere Informationen finden Sie [im Benutzerhandbuch für diagnosticsource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="2166b-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="2166b-108">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="2166b-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2166b-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2166b-109">Requirements</span></span>

<span data-ttu-id="2166b-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="2166b-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="2166b-111">**Assembly:** System (in "System. dll")</span><span class="sxs-lookup"><span data-stu-id="2166b-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="2166b-112">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="2166b-112">**.NET Framework versions:** Available since 2.0.</span></span>
