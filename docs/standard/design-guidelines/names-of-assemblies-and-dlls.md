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
ms.openlocfilehash: 8e20d77c20be8dc74723117f3b0910ecc2090ef7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130974"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="08044-102">Namen von Assemblys und DLLs</span><span class="sxs-lookup"><span data-stu-id="08044-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="08044-103">Eine Assembly ist die Einheit der Bereitstellung und Identität für verwalteten Code Programme.</span><span class="sxs-lookup"><span data-stu-id="08044-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="08044-104">Obwohl Assemblys eine oder mehrere Dateien umfassen können, in der Regel ordnet eine Assembly mit einer DLL 1: 1.</span><span class="sxs-lookup"><span data-stu-id="08044-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="08044-105">Aus diesem Grund wird in diesem Abschnitt beschrieben, nur DLL Benennungskonventionen, die Sie dann den Benennungskonventionen für Assembly zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="08044-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="08044-106">**✓ DO** wählen Sie Namen für die Assembly DLLs, die große Blöcke von Funktionen, z. B. "System.Data" vorschlagen.</span><span class="sxs-lookup"><span data-stu-id="08044-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="08044-107">Keine Assembly und DLL-Namen, Namespace-Namen entsprechen, aber es ist sinnvoll, führen den Namen des Namespaces, Assemblys.</span><span class="sxs-lookup"><span data-stu-id="08044-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="08044-108">Eine gute Faustregel ist, der basierend auf das gemeinsame Präfix des Namespaces in der Assembly enthaltenen DLL-name.</span><span class="sxs-lookup"><span data-stu-id="08044-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="08044-109">Z. B. eine Assembly mit zwei Namespaces `MyCompany.MyTechnology.FirstFeature` und `MyCompany.MyTechnology.SecondFeature`, könnte `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="08044-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="08044-110">**✓ CONSIDER** naming DLLs nach dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="08044-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="08044-111">wo `<Component>` enthält eine oder mehrere Punkte getrennte Klauseln.</span><span class="sxs-lookup"><span data-stu-id="08044-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="08044-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="08044-112">For example:</span></span>  
  
 <span data-ttu-id="08044-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="08044-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="08044-114">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="08044-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="08044-115">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="08044-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08044-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08044-116">See also</span></span>

- [<span data-ttu-id="08044-117">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="08044-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="08044-118">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="08044-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
