---
title: Versionstolerante Serialisierungsrückrufe
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
ms.openlocfilehash: ad162f24042f30eabee7a1fad2025072b26d9af5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289372"
---
# <a name="version-tolerant-serialization-callbacks"></a><span data-ttu-id="52e3f-102">Versionstolerante Serialisierungsrückrufe</span><span class="sxs-lookup"><span data-stu-id="52e3f-102">Version-Tolerant Serialization Callbacks</span></span>

<span data-ttu-id="52e3f-103">Die von den Klassen <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> und <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> unterstützten Methoden für versionstolerante Serialisierungsrückrufe werden vom Datenvertrags-Programmiermodell vollständig unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52e3f-103">The data contract programming model fully supports the version-tolerant serialization callback methods that the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> classes support.</span></span>  
  
## <a name="version-tolerant-attributes"></a><span data-ttu-id="52e3f-104">Versionstolerante Attribute</span><span class="sxs-lookup"><span data-stu-id="52e3f-104">Version-Tolerant Attributes</span></span>  

 <span data-ttu-id="52e3f-105">Es gibt vier Rückrufattribute.</span><span class="sxs-lookup"><span data-stu-id="52e3f-105">There are four callback attributes.</span></span> <span data-ttu-id="52e3f-106">Jedes Attribut kann für eine Methode angewendet werden, die die Serialisierungs-/Deserialisierung-Engine zu verschiedenen Zeiten aufruft.</span><span class="sxs-lookup"><span data-stu-id="52e3f-106">Each attribute can be applied to a method that the serialization/deserialization engine calls at various times.</span></span> <span data-ttu-id="52e3f-107">In der folgenden Tabelle wird erläutert, wann die einzelnen Attribute verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52e3f-107">The table below explains when to use each attribute.</span></span>  
  
|<span data-ttu-id="52e3f-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="52e3f-108">Attribute</span></span>|<span data-ttu-id="52e3f-109">Beim Aufruf der entsprechenden Methode</span><span class="sxs-lookup"><span data-stu-id="52e3f-109">When the corresponding method is called</span></span>|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="52e3f-110">Der Aufruf erfolgt vor dem Serialisieren des Typs.</span><span class="sxs-lookup"><span data-stu-id="52e3f-110">Called before serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="52e3f-111">Der Aufruf erfolgt nach dem Serialisieren des Typs.</span><span class="sxs-lookup"><span data-stu-id="52e3f-111">Called after serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="52e3f-112">Der Aufruf erfolgt vor dem Deserialisieren des Typs.</span><span class="sxs-lookup"><span data-stu-id="52e3f-112">Called before deserializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="52e3f-113">Der Aufruf erfolgt nach dem Deserialisieren des Typs.</span><span class="sxs-lookup"><span data-stu-id="52e3f-113">Called after deserializing the type.</span></span>|  
  
 <span data-ttu-id="52e3f-114">Diese Methode muss einen <xref:System.Runtime.Serialization.StreamingContext>-Parameter akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="52e3f-114">The methods must accept a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span>  
  
 <span data-ttu-id="52e3f-115">Diese Methoden sind in erster Linie für die Verwendung mit der Versionsverwaltung oder der Initialisierung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="52e3f-115">These methods are primarily intended for use with versioning or initialization.</span></span> <span data-ttu-id="52e3f-116">Während der Deserialisierung werden keine Konstruktoren aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="52e3f-116">During deserialization, no constructors are called.</span></span> <span data-ttu-id="52e3f-117">Datenmember werden deshalb möglicherweise nicht ordnungsgemäß initialisiert (auf beabsichtigte Standardwerte), falls die Daten für diese Member im eingehenden Stream fehlen. Das kann z.&#160;B. der Fall sein, wenn die Daten aus einer früheren Version eines Typs stammen, bei dem einige Datenmember fehlen.</span><span class="sxs-lookup"><span data-stu-id="52e3f-117">Therefore, data members may not be correctly initialized (to intended default values) if the data for these members is missing in the incoming stream, for example, if the data comes from a previous version of a type that is missing some data members.</span></span> <span data-ttu-id="52e3f-118">Verwenden Sie die mit <xref:System.Runtime.Serialization.OnDeserializingAttribute> gekennzeichnete Methode, wie im folgenden Beispiel dargestellt, um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="52e3f-118">To correct this, use the callback method marked with the <xref:System.Runtime.Serialization.OnDeserializingAttribute>, as shown in the following example.</span></span>  
  
 <span data-ttu-id="52e3f-119">Mit jedem der oben aufgeführten Rückrufattribute kann nur eine Methode pro Typ gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="52e3f-119">You can mark only one method per type with each of the preceding callback attributes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="52e3f-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52e3f-120">Example</span></span>  

 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="52e3f-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52e3f-121">See also</span></span>

- <xref:System.Runtime.Serialization.OnSerializingAttribute>
- <xref:System.Runtime.Serialization.OnSerializedAttribute>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>
- <xref:System.Runtime.Serialization.StreamingContext>
- [<span data-ttu-id="52e3f-122">Versions tolerante Serialisierung</span><span class="sxs-lookup"><span data-stu-id="52e3f-122">Version Tolerant Serialization</span></span>](../../../standard/serialization/version-tolerant-serialization.md)
