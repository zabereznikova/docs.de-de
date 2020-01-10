---
title: Feld "HttpWebRequest. _CoreResponse"
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: d16936f6984e73a886f5f48e05b53501ced63c1b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740449"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="b431a-102">HttpWebRequest.\_Feld "coreresponse"</span><span class="sxs-lookup"><span data-stu-id="b431a-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="b431a-103">`HttpWebRequest._CoreResponse` ist ein Objekt (entweder [coreresponsedata](coreresponsedata.md) oder ein <xref:System.Exception>), das das Ergebnis der HTTP-Antwort Analyse enthält.</span><span class="sxs-lookup"><span data-stu-id="b431a-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="b431a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b431a-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="b431a-105">Diese API ist nicht für die direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b431a-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="b431a-106">Stattdessen sollten Sie einen <xref:System.Diagnostics.DiagnosticSource> zum Anschließen von Netzwerkcode verwenden.</span><span class="sxs-lookup"><span data-stu-id="b431a-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="b431a-107">Weitere Informationen finden Sie [im Benutzerhandbuch für diagnosticsource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="b431a-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="b431a-108">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="b431a-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b431a-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b431a-109">Requirements</span></span>

<span data-ttu-id="b431a-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="b431a-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="b431a-111">**Assembly:** System (in "System. dll")</span><span class="sxs-lookup"><span data-stu-id="b431a-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="b431a-112">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="b431a-112">**.NET Framework versions:** Available since 2.0.</span></span>
