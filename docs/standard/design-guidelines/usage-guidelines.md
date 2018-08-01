---
title: Verwendungsrichtlinien
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02905c193387f78430ce1885449055060d07bf82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571032"
---
# <a name="usage-guidelines"></a><span data-ttu-id="39e24-102">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="39e24-102">Usage Guidelines</span></span>
<span data-ttu-id="39e24-103">Dieser Abschnitt enthält Richtlinien für die Verwendung von gemeinsamer Typen in öffentlich zugängliche-APIs.</span><span class="sxs-lookup"><span data-stu-id="39e24-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="39e24-104">Er behandelt die Nutzung des integrierten Framework-Typen (z. B. Serialisierungsattribute) und allgemeine Operatoren überladen.</span><span class="sxs-lookup"><span data-stu-id="39e24-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>  
  
 <span data-ttu-id="39e24-105">Die <xref:System.IDisposable?displayProperty=nameWithType> Schnittstelle wird nicht in diesem Abschnitt behandelt, aber es wird erläutert, der [Dispose-Muster](../../../docs/standard/design-guidelines/dispose-pattern.md) Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="39e24-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39e24-106">Richtlinien und zusätzliche Informationen über andere gängige integrierte .NET Framework-Typen finden Sie unter den Referenzthemen für Folgendes: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39e24-106">For guidelines and additional information about about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39e24-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="39e24-107">In This Section</span></span>  
 [<span data-ttu-id="39e24-108">Arrays</span><span class="sxs-lookup"><span data-stu-id="39e24-108">Arrays</span></span>](../../../docs/standard/design-guidelines/arrays.md)  
 [<span data-ttu-id="39e24-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="39e24-109">Attributes</span></span>](../../../docs/standard/design-guidelines/attributes.md)  
 [<span data-ttu-id="39e24-110">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="39e24-110">Collections</span></span>](/cpp/mfc/collections)  
 [<span data-ttu-id="39e24-111">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="39e24-111">Serialization</span></span>](../../../docs/standard/design-guidelines/serialization.md)  
 [<span data-ttu-id="39e24-112">Verwendung von System.Xml</span><span class="sxs-lookup"><span data-stu-id="39e24-112">System.Xml Usage</span></span>](../../../docs/standard/design-guidelines/system-xml-usage.md)  
 [<span data-ttu-id="39e24-113">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="39e24-113">Equality Operators</span></span>](../../../docs/standard/design-guidelines/equality-operators.md)  
 <span data-ttu-id="39e24-114">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="39e24-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="39e24-115">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="39e24-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e24-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39e24-116">See Also</span></span>  
 [<span data-ttu-id="39e24-117">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="39e24-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
