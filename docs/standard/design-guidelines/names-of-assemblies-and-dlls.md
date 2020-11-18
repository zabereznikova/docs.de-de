---
title: Namen von Assemblys und DLLs
description: Erfahren Sie mehr über Richtlinien für das Benennen von Assemblys und Dynamic Link Libraries (DLLs). Eine Assembly kann eine oder mehrere Dateien umfassen, Sie ordnet jedoch in der Regel eins-zu-eins einer DLL zu.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: 2d1484889eb7db537de970c31109f26a6d61ad8d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830050"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="2647f-104">Namen von Assemblys und DLLs</span><span class="sxs-lookup"><span data-stu-id="2647f-104">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="2647f-105">Eine Assembly ist die Bereitstellungs Einheit und Identität für verwaltete Code Programme.</span><span class="sxs-lookup"><span data-stu-id="2647f-105">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="2647f-106">Assemblys können sich über eine oder mehrere Dateien erstrecken. in der Regel ordnet eine Assembly eins-zu-eins einer DLL zu.</span><span class="sxs-lookup"><span data-stu-id="2647f-106">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="2647f-107">In diesem Abschnitt werden daher nur dll-Benennungs Konventionen beschrieben, die dann assemblybenennungs Konventionen zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="2647f-107">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>

 <span data-ttu-id="2647f-108">✔️ Wählen Sie Namen für die assemblydlls aus, die große Funktionsblöcke vorschlagen, wie z. b. System. Data.</span><span class="sxs-lookup"><span data-stu-id="2647f-108">✔️ DO choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>

 <span data-ttu-id="2647f-109">Assemblynamen und DLL-Namen müssen nicht den Namespace Namen entsprechen, aber es ist sinnvoll, beim Benennen von Assemblys den Namespace Namen zu befolgen.</span><span class="sxs-lookup"><span data-stu-id="2647f-109">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="2647f-110">Eine gute Faustregel besteht darin, die dll basierend auf dem gemeinsamen Präfix der in der Assembly enthaltenen Namespaces zu benennen.</span><span class="sxs-lookup"><span data-stu-id="2647f-110">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="2647f-111">Beispielsweise kann eine Assembly mit zwei Namespaces ( `MyCompany.MyTechnology.FirstFeature` und) `MyCompany.MyTechnology.SecondFeature` aufgerufen werden `MyCompany.MyTechnology.dll` .</span><span class="sxs-lookup"><span data-stu-id="2647f-111">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>

 <span data-ttu-id="2647f-112">✔️ in Erwägung gezogen, DLLs gemäß folgendem Muster zu benennen:</span><span class="sxs-lookup"><span data-stu-id="2647f-112">✔️ CONSIDER naming DLLs according to the following pattern:</span></span>

 `<Company>.<Component>.dll`

 <span data-ttu-id="2647f-113">, wobei `<Component>` eine oder mehrere durch Punkte getrennte Klauseln enthält.</span><span class="sxs-lookup"><span data-stu-id="2647f-113">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="2647f-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2647f-114">For example:</span></span>

 <span data-ttu-id="2647f-115">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="2647f-115">`Litware.Controls.dll`.</span></span>

 <span data-ttu-id="2647f-116">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="2647f-116">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2647f-117">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="2647f-117">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2647f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2647f-118">See also</span></span>

- [<span data-ttu-id="2647f-119">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="2647f-119">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="2647f-120">Benennungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="2647f-120">Naming Guidelines</span></span>](naming-guidelines.md)
