---
title: "Entschärfung: Pfadnormalisierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e30099e315f88bd051dca2e1f6c83d1bccc49569
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="a2aa7-102">Entschärfung: Pfadnormalisierung</span><span class="sxs-lookup"><span data-stu-id="a2aa7-102">Mitigation: Path Normalization</span></span>
<span data-ttu-id="a2aa7-103">Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an hat sich die Pfadnormalisierung in .NET Framework geändert.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-103">Starting with apps the target  the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="a2aa7-104">Was ist Pfadnormalisierung?</span><span class="sxs-lookup"><span data-stu-id="a2aa7-104">What is path normalization?</span></span>  
 <span data-ttu-id="a2aa7-105">Das Normalisieren eines Pfads beinhaltet das Verändern der Zeichenfolge, die einen Pfad oder eine Datei kennzeichnet, in einer Weise, dass sie einem gültigen Pfad im Zielbetriebssystem entspricht.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-105">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="a2aa7-106">Normalisierung umfasst ist in der Regel:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-106">Normalization typically involves:</span></span>  
  
-   <span data-ttu-id="a2aa7-107">Die Kanonisierung von Komponenten- und Verzeichnistrennzeichen.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-107">Canonicalizing component and directory separators.</span></span>  
  
-   <span data-ttu-id="a2aa7-108">Die Anwendung des aktuellen Verzeichnisses auf einen relativen Pfad.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-108">Applying the current directory to a relative path.</span></span>  
  
-   <span data-ttu-id="a2aa7-109">Die Auswertung des relativen Verzeichnisses (`.`) oder des übergeordneten Verzeichnisses (`..`) in einem Pfad.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-109">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
-   <span data-ttu-id="a2aa7-110">Das Verkürzen um angegebene Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-110">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="a2aa7-111">Die Änderungen</span><span class="sxs-lookup"><span data-stu-id="a2aa7-111">The changes</span></span>  
 <span data-ttu-id="a2aa7-112">Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an hat sich die Pfadnormalisierung in folgender Weise geändert:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-112">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization has changed in the following ways:</span></span>  
  
-   <span data-ttu-id="a2aa7-113">Die Runtime greift auf die Funktion [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) des Betriebssystems zurück, um Pfade zu normalisieren.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-113">The runtime defers to the operating system's [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) function to normalize paths.</span></span>  
  
-   <span data-ttu-id="a2aa7-114">Die Normalisierung beinhaltet nicht mehr das Verkürzen des Endes von Verzeichnissegmenten (etwa im Fall eines Leerzeichens am Ende eines Verzeichnisnamens).</span><span class="sxs-lookup"><span data-stu-id="a2aa7-114">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
-   <span data-ttu-id="a2aa7-115">Unterstützung für Gerätepfadsyntax mit vollem Vertrauen, einschließlich `\\.\` und `\\?\` für Datei-E/A-APIs in mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-115">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
-   <span data-ttu-id="a2aa7-116">Die Runtime überprüft Gerätesyntaxpfade nicht.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-116">The runtime does not validate device syntax paths.</span></span>  
  
-   <span data-ttu-id="a2aa7-117">Die Verwendung von Gerätesyntax für den Zugriff auf alternative Datenströme wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-117">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="a2aa7-118">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="a2aa7-118">Impact</span></span>  
 <span data-ttu-id="a2aa7-119">Für Apps mit der Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder höher sind diese Änderungen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-119">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later, these changes are on  by default.</span></span> <span data-ttu-id="a2aa7-120">Sie sollten die Leistung verbessern und Methoden zugleich den Zugriff auf zuvor nicht zugängliche Pfade ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-120">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
 <span data-ttu-id="a2aa7-121">Apps mit der Zielplattform [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früheren Versionen, die unter [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder höher ausgeführt werden, sind von dieser Änderung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="a2aa7-121">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions but are running under the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="a2aa7-122">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="a2aa7-122">Mitigation</span></span>  
 <span data-ttu-id="a2aa7-123">Apps mit der Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder höher können sich gegen diese Änderung entscheiden und Legacynormalisierung verwenden, indem dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei Folgendes hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-123">Apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
 <span data-ttu-id="a2aa7-124">Apps mit der Zielplattform [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] oder früher, die unter [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder höher ausgeführt werden, können die Änderungen an der Pfadnormalisierung verwenden, indem dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei die folgende Zeile hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="a2aa7-124">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or earlier but are running on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2aa7-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2aa7-125">See Also</span></span>  
 [<span data-ttu-id="a2aa7-126">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="a2aa7-126">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

