---
title: XmlReader. kreatesqlreader-Methode (System. Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: c65ef7c073175488c11c5e912a44d46fd4319209
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215449"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="72d50-102">XmlReader.CreateSqlReader-Methode</span><span class="sxs-lookup"><span data-stu-id="72d50-102">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="72d50-103">Erstellt mit dem angegebenen Stream, den Einstellungen und den Kontextinformationen für Analysezwecke eine neue <xref:System.Xml.XmlReader>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="72d50-103">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input, 
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="72d50-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="72d50-104">Parameters</span></span>

- <span data-ttu-id="72d50-105">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="72d50-105">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="72d50-106">Der Stream, der die XML-Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="72d50-106">The stream that contains the XML data.</span></span>

- <span data-ttu-id="72d50-107">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="72d50-107">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="72d50-108">Die Einstellungen für die neue <xref:System.Xml.XmlReader>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="72d50-108">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="72d50-109">Dieser Wert kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="72d50-109">This value can be `null`.</span></span>

- <span data-ttu-id="72d50-110">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="72d50-110">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="72d50-111">Die Kontextinformationen, die zum Analysieren des XML-Fragments erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="72d50-111">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="72d50-112">Dieser Wert kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="72d50-112">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="72d50-113">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="72d50-113">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="72d50-114">Ein Objekt, mit dem die im Stream enthaltenen XML-Daten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="72d50-114">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="72d50-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="72d50-115">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="72d50-116">Die `XmlReader.CreateSqlReader`-Methode ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72d50-116">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="72d50-117">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="72d50-117">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="72d50-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="72d50-118">Requirements</span></span>

<span data-ttu-id="72d50-119">**Namespace:** <xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="72d50-119">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="72d50-120">**Assembly:** System. Xml. dll</span><span class="sxs-lookup"><span data-stu-id="72d50-120">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="72d50-121">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="72d50-121">**.NET Framework versions:** Available since 2.0.</span></span>
