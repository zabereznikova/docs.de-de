---
title: XmlReader.CreateSqlReader-Methode (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 7bd2ef5158516acede47f73f9937d06159bc16c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155738"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="eabd4-102">XmlReader.CreateSqlReader-Methode</span><span class="sxs-lookup"><span data-stu-id="eabd4-102">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="eabd4-103">Erstellt mit dem angegebenen Stream, den Einstellungen und den Kontextinformationen für Analysezwecke eine neue <xref:System.Xml.XmlReader>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="eabd4-103">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input,
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="eabd4-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="eabd4-104">Parameters</span></span>

- <span data-ttu-id="eabd4-105">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="eabd4-105">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="eabd4-106">Der Stream, der die XML-Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="eabd4-106">The stream that contains the XML data.</span></span>

- <span data-ttu-id="eabd4-107">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="eabd4-107">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="eabd4-108">Die Einstellungen für die neue <xref:System.Xml.XmlReader>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="eabd4-108">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="eabd4-109">Dieser Wert kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="eabd4-109">This value can be `null`.</span></span>

- <span data-ttu-id="eabd4-110">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="eabd4-110">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="eabd4-111">Die Kontextinformationen, die zum Analysieren des XML-Fragments erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="eabd4-111">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="eabd4-112">Dieser Wert kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="eabd4-112">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="eabd4-113">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="eabd4-113">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="eabd4-114">Ein Objekt, mit dem die im Stream enthaltenen XML-Daten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="eabd4-114">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="eabd4-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="eabd4-115">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="eabd4-116">Die `XmlReader.CreateSqlReader` Methode ist intern und soll nicht direkt in Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eabd4-116">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="eabd4-117">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="eabd4-117">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="eabd4-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eabd4-118">Requirements</span></span>

<span data-ttu-id="eabd4-119">**Namespace:**<xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="eabd4-119">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="eabd4-120">**Montage:** System.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="eabd4-120">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="eabd4-121">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="eabd4-121">**.NET Framework versions:** Available since 2.0.</span></span>
