---
title: Namespaces und DTDs im DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1e9b55c4-76ad-4f54-8d96-7ce4b4cf1e05
ms.openlocfilehash: 22762e3a7003d9b28a53c7b500829aaa41924c6d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710595"
---
# <a name="namespaces-and-dtds-in-the-dom"></a><span data-ttu-id="7317e-102">Namespaces und DTDs im DOM</span><span class="sxs-lookup"><span data-stu-id="7317e-102">Namespaces and DTDs in the DOM</span></span>
<span data-ttu-id="7317e-103">DTDs (Document Type Definition) erschweren die Namespace-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="7317e-103">Document type definitions (DTDs) complicate namespace support.</span></span> <span data-ttu-id="7317e-104">Das folgende XML-Beispiel enthält Standardattribute, deren Namen Doppelpunkte enthalten.</span><span class="sxs-lookup"><span data-stu-id="7317e-104">For example, the following XML contains default attributes containing colons in their names.</span></span>  
  
```xml  
<!ATTLIST item x:id CDATA #IMPLIED>  
```  
  
 <span data-ttu-id="7317e-105">Folgende Auflösungen sind möglich, wenn dieses Konstrukt zulässig ist:</span><span class="sxs-lookup"><span data-stu-id="7317e-105">The following are possible resolutions if this construct is allowed:</span></span>  
  
- <span data-ttu-id="7317e-106">`x:` wird als Namespacepräfix behandelt, aber dieses Präfix muss mit einer `xmlns:x`-Namespacedeklaration auflösbar sein, die auch an einer beliebigen Stelle in der DTD vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="7317e-106">The `x:` is treated as a namespace prefix, but this prefix must be resolvable using an `xmlns:x` namespace declaration, which must also exist somewhere in the DTD.</span></span> <span data-ttu-id="7317e-107">Wenn das Präfix einem anderen Element im Instanzdokument zugeordnet wird, stellt dies einen Fehler dar.</span><span class="sxs-lookup"><span data-stu-id="7317e-107">It is an error to map this prefix to something different in the instance document.</span></span>  
  
- <span data-ttu-id="7317e-108">`x:` wird als Namespacepräfix behandelt, aber dieses Präfix wird immer im Kontext der Instanzelemente aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="7317e-108">The `x:` is treated as a namespace prefix, but this prefix is always resolved in the context of the instance elements.</span></span> <span data-ttu-id="7317e-109">Das bedeutet, dass das Präfix im Grunde verschiedenen Namespace-URIs (Uniform Resource Identifier) zugeordnet werden könnte, je nachdem, in welchem Namespacegültigkeitsbereich das `item`-Element auftritt.</span><span class="sxs-lookup"><span data-stu-id="7317e-109">This means the prefix could actually map to different namespace Uniform Resource Identifiers (URIs), depending on the namespace scope in which the `item` element appears.</span></span> <span data-ttu-id="7317e-110">Dieses Verhalten ist besser vorhersagbar als die im vorherigen Punkt beschriebene Auflösung; es hat jedoch andere komplizierte Auswirkungen, da es die Materialisierung der Standardattribute erfordert.</span><span class="sxs-lookup"><span data-stu-id="7317e-110">This behavior is more predictable than the resolution given in the earlier bullet, but it has other complicated ramifications because it requires the default attributes be materialized.</span></span>  
  
- <span data-ttu-id="7317e-111">Der Doppelpunkt wird ignoriert, da er in einer DTD vorkommt, und der Name des Attributs ist `x:y`. Es ist kein Präfix und kein Namespace-URI vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7317e-111">The colon is ignored because it is in a DTD, and the name of the attribute is `x:y`, no prefix and no namespace URI.</span></span>  
  
- <span data-ttu-id="7317e-112">Der Doppelpunkt im Standardattribut löst eine Ausnahme aus, die besagt, dass Doppelpunkte in Namen innerhalb einer DTD nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7317e-112">The colon in the default attribute throws an exception, saying that colons in names inside a DTD are not supported.</span></span> <span data-ttu-id="7317e-113">Dies führt zu einem vorhersagbaren Verhalten, bedeutet aber auch, dass Sie nur einige der vom W3C (World Wide Web Consortium) veröffentlichten DTDs laden können.</span><span class="sxs-lookup"><span data-stu-id="7317e-113">This results in a predictable behavior, but means you cannot load many of the World Wide Web Consortium (W3C) published DTDs.</span></span>  
  
- <span data-ttu-id="7317e-114">Wenn der Benutzer eine DTD-Validierung anfordert, wird die Unterstützung von Namespaces für das gesamte Dokument deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7317e-114">When the user requests DTD validation, namespace support for the entire document is turned off.</span></span> <span data-ttu-id="7317e-115">Dadurch können W3C-DTDs geladen werden, und es ergibt sich ein vorhersagbares Verhalten.</span><span class="sxs-lookup"><span data-stu-id="7317e-115">This makes it possible to load W3C DTDs and results in a predictable behavior.</span></span>  
  
 <span data-ttu-id="7317e-116">Beim XML-Code in Microsoft .NET Framework wird die zweite Option implementiert, um maximale Kompatibilität mit der W3C-Spezifikation zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="7317e-116">The XML in the Microsoft .NET Framework implements the second option for maximum W3C compatibility.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7317e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7317e-117">See also</span></span>

- [<span data-ttu-id="7317e-118">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="7317e-118">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
