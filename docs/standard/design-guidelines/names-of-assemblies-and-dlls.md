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
author: KrzysztofCwalina
ms.openlocfilehash: 1aeef9e1be6e5fe747f440a8cb7f21095cb22f49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945495"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="88e79-102">Namen von Assemblys und DLLs</span><span class="sxs-lookup"><span data-stu-id="88e79-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="88e79-103">Eine Assembly ist die Einheit der Bereitstellung und Identität für verwalteten Code Programme.</span><span class="sxs-lookup"><span data-stu-id="88e79-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="88e79-104">Obwohl Assemblys eine oder mehrere Dateien umfassen können, in der Regel ordnet eine Assembly mit einer DLL 1: 1.</span><span class="sxs-lookup"><span data-stu-id="88e79-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="88e79-105">Aus diesem Grund wird in diesem Abschnitt beschrieben, nur DLL Benennungskonventionen, die Sie dann den Benennungskonventionen für Assembly zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="88e79-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="88e79-106">**✓ DO** wählen Sie Namen für die Assembly DLLs, die große Blöcke von Funktionen, z. B. "System.Data" vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="88e79-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="88e79-107">Keine Assembly und DLL-Namen, Namespace-Namen entsprechen, aber es ist sinnvoll, führen den Namen des Namespaces, Assemblys.</span><span class="sxs-lookup"><span data-stu-id="88e79-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="88e79-108">Eine gute Faustregel ist, der basierend auf das gemeinsame Präfix des Namespaces in der Assembly enthaltenen DLL-name.</span><span class="sxs-lookup"><span data-stu-id="88e79-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="88e79-109">Z. B. eine Assembly mit zwei Namespaces `MyCompany.MyTechnology.FirstFeature` und `MyCompany.MyTechnology.SecondFeature`, könnte `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="88e79-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="88e79-110">**✓ CONSIDER** naming DLLs nach dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="88e79-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="88e79-111">wo `<Component>` enthält eine oder mehrere Punkte getrennte Klauseln.</span><span class="sxs-lookup"><span data-stu-id="88e79-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="88e79-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88e79-112">For example:</span></span>  
  
 <span data-ttu-id="88e79-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="88e79-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="88e79-114">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="88e79-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="88e79-115">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="88e79-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88e79-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88e79-116">See also</span></span>

- [<span data-ttu-id="88e79-117">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="88e79-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="88e79-118">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="88e79-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
