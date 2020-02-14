---
title: Message. Write-starteaders-Methode (System. Service Model. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: c826e6a3b976e5705e9815586441e8a25b64f76e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214864"
---
# <a name="messagewritestartheaders-method"></a><span data-ttu-id="513a4-102">Message. Write-starteaders-Methode</span><span class="sxs-lookup"><span data-stu-id="513a4-102">Message.WriteStartHeaders Method</span></span>

<span data-ttu-id="513a4-103">Schreibt den Start Header in eine XML-Datei, indem die <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="513a4-103">Writes the start header into an XML file by calling the <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> method.</span></span>

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a><span data-ttu-id="513a4-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="513a4-104">Parameters</span></span>

- <span data-ttu-id="513a4-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span><span class="sxs-lookup"><span data-stu-id="513a4-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span></span>\
  <span data-ttu-id="513a4-106">Der Writer, der zum Schreiben des Start Headers in eine XML-Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="513a4-106">The writer that is used to write the start header into an XML file.</span></span>

## <a name="remarks"></a><span data-ttu-id="513a4-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="513a4-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="513a4-108">Die `Message.WriteStartHeaders`-Methode ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="513a4-108">The `Message.WriteStartHeaders` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="513a4-109">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="513a4-109">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="513a4-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="513a4-110">Requirements</span></span>

<span data-ttu-id="513a4-111">**Namespace:** <xref:System.ServiceModel.Channels></span><span class="sxs-lookup"><span data-stu-id="513a4-111">**Namespace:** <xref:System.ServiceModel.Channels></span></span>

<span data-ttu-id="513a4-112">**Assembly:** System. Service Model. dll</span><span class="sxs-lookup"><span data-stu-id="513a4-112">**Assembly:** System.ServiceModel.dll</span></span>

<span data-ttu-id="513a4-113">**.NET Framework Versionen:** Verfügbar seit 3,0.</span><span class="sxs-lookup"><span data-stu-id="513a4-113">**.NET Framework versions:** Available since 3.0.</span></span>
