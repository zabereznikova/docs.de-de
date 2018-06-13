---
title: Namen von Assemblys und DLLs
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6cf175472d68e99598dd56e170bee3d37ae3c2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570424"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="59717-102">Namen von Assemblys und DLLs</span><span class="sxs-lookup"><span data-stu-id="59717-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="59717-103">Eine Assembly ist die Einheit der Bereitstellung und Identität für verwalteten Code Programme.</span><span class="sxs-lookup"><span data-stu-id="59717-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="59717-104">Obwohl Assemblys eine oder mehrere Dateien umfassen können, in der Regel ordnet eine Assembly eine DLL eins zu eins.</span><span class="sxs-lookup"><span data-stu-id="59717-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="59717-105">Dieser Abschnitt beschreibt daher nur DLL Benennungskonventionen, der dann Benennungskonventionen Assembly zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="59717-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="59717-106">**Führen Sie ✓** wählen Sie Namen für die Assembly DLLs, die große Blöcke von Funktionen, z. B. "System.Data" vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="59717-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="59717-107">Assembly- und DLL-Namen müssen den Namespace-Namen entsprechen, aber es ist angemessen, des Namespacenamens befolgen beim Benennen von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="59717-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="59717-108">Eine gute Faustregel ist, der basierend auf einem gemeinsamen Präfix der Namespaces in der Assembly enthaltenen DLL-name.</span><span class="sxs-lookup"><span data-stu-id="59717-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="59717-109">Angenommen, eine Assembly mit zwei Namespaces `MyCompany.MyTechnology.FirstFeature` und `MyCompany.MyTechnology.SecondFeature`, aufgerufen werden `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="59717-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="59717-110">**✓ GGF.** naming DLLs nach dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="59717-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="59717-111">wobei `<Component>` enthält eine oder mehrere Punkte getrennte Klauseln.</span><span class="sxs-lookup"><span data-stu-id="59717-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="59717-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="59717-112">For example:</span></span>  
  
 <span data-ttu-id="59717-113">`Litware.Controls.dll`</span><span class="sxs-lookup"><span data-stu-id="59717-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="59717-114">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="59717-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="59717-115">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="59717-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59717-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59717-116">See Also</span></span>  
 [<span data-ttu-id="59717-117">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="59717-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="59717-118">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="59717-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
