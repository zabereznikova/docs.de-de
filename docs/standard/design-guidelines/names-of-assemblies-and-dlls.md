---
title: Namen von Assemblys und DLLs
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: eebccba0b923b04333f289a85330d190c31013ab
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709256"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="6bcd4-102">Namen von Assemblys und DLLs</span><span class="sxs-lookup"><span data-stu-id="6bcd4-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="6bcd4-103">Eine Assembly ist die Bereitstellungs Einheit und Identität für verwaltete Code Programme.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="6bcd4-104">Assemblys können sich über eine oder mehrere Dateien erstrecken. in der Regel ordnet eine Assembly eins-zu-eins einer DLL zu.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="6bcd4-105">In diesem Abschnitt werden daher nur dll-Benennungs Konventionen beschrieben, die dann assemblybenennungs Konventionen zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="6bcd4-106">**✓ DO** wählen Sie Namen für die Assembly DLLs, die große Blöcke von Funktionen, z. B. "System.Data" vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="6bcd4-107">Assemblynamen und DLL-Namen müssen nicht den Namespace Namen entsprechen, aber es ist sinnvoll, beim Benennen von Assemblys den Namespace Namen zu befolgen.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="6bcd4-108">Eine gute Faustregel besteht darin, die dll basierend auf dem gemeinsamen Präfix der in der Assembly enthaltenen Namespaces zu benennen.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="6bcd4-109">Beispielsweise kann eine Assembly mit zwei Namespaces (`MyCompany.MyTechnology.FirstFeature` und `MyCompany.MyTechnology.SecondFeature``MyCompany.MyTechnology.dll`aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="6bcd4-110">**✓ CONSIDER** naming DLLs nach dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="6bcd4-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="6bcd4-111">, wobei `<Component>` eine oder mehrere durch Punkte getrennte Klauseln enthält.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="6bcd4-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6bcd4-112">For example:</span></span>  
  
 <span data-ttu-id="6bcd4-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="6bcd4-114">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="6bcd4-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6bcd4-115">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="6bcd4-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bcd4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bcd4-116">See also</span></span>

- [<span data-ttu-id="6bcd4-117">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="6bcd4-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="6bcd4-118">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="6bcd4-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
