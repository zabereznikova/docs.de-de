---
title: XmlReader. kreatesqlreader-Methode (System. Xml)
author: mairaw
ms.author: mairaw
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 302be4eff32d2c96a1571d291e0b289e77694db8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582781"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="ea720-102">XmlReader. kreatesqlreader-Methode</span><span class="sxs-lookup"><span data-stu-id="ea720-102">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="ea720-103">Erstellt mit dem angegebenen Stream, den Einstellungen und den Kontextinformationen für Analysezwecke eine neue <xref:System.Xml.XmlReader>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="ea720-103">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input, 
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="ea720-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea720-104">Parameters</span></span>

- <span data-ttu-id="ea720-105">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="ea720-105">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="ea720-106">Der Stream, der die XML-Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="ea720-106">The stream that contains the XML data.</span></span>

- <span data-ttu-id="ea720-107">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="ea720-107">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="ea720-108">Die Einstellungen für die neue <xref:System.Xml.XmlReader>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="ea720-108">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="ea720-109">Dieser Wert kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="ea720-109">This value can be `null`.</span></span>

- <span data-ttu-id="ea720-110">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="ea720-110">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="ea720-111">Die Kontextinformationen, die zum Analysieren des XML-Fragments erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ea720-111">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="ea720-112">Dieser Wert kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="ea720-112">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="ea720-113">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="ea720-113">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="ea720-114">Ein Objekt, mit dem die im Stream enthaltenen XML-Daten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="ea720-114">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea720-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea720-115">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="ea720-116">Die `XmlReader.CreateSqlReader`-Methode ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ea720-116">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ea720-117">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="ea720-117">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ea720-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea720-118">Requirements</span></span>

<span data-ttu-id="ea720-119">**Namespace:** <xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="ea720-119">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="ea720-120">**Assembly:** System. Xml. dll</span><span class="sxs-lookup"><span data-stu-id="ea720-120">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="ea720-121">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="ea720-121">**.NET Framework versions:** Available since 2.0.</span></span>
