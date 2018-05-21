---
title: 'Entschärfung: Pfadtrennzeichen für ZipArchiveEntry.FullName'
ms.date: 03/30/2017
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3940cf8d1ebda668925a5c461b84a8bc61550476
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a><span data-ttu-id="8cd38-102">Entschärfung: Pfadtrennzeichen für ZipArchiveEntry.FullName</span><span class="sxs-lookup"><span data-stu-id="8cd38-102">Mitigation: ZipArchiveEntry.FullName Path Separator</span></span>
<span data-ttu-id="8cd38-103">Von Apps für die Zielplattform [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] an wurde das in der Eigenschaft <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> verwendete Pfadtrennzeichen vom umgekehrten Schrägstrich („\\“), der in früheren Versionen von .NET Framework verwendet wurde, in einen einfachen Schrägstrich („/“) geändert.</span><span class="sxs-lookup"><span data-stu-id="8cd38-103">Starting with apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the path separator used in the <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> property has changed from the backslash ("\\") used in previous versions of the .NET Framework to a forward slash ("/").</span></span>   <span data-ttu-id="8cd38-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType>-Objekte werden durch Aufrufen einer der Überladungen der <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>-Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="8cd38-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> objects are created by calling one of the overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="8cd38-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="8cd38-105">Impact</span></span>  
 <span data-ttu-id="8cd38-106">Die Änderung bringt die .NET-Implementierung in Einklang mit Abschnitt 4.4.17.1 der [ZIP-Dateiformatspezifikation](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) und ermöglicht es, dass ZIP-Archive auf Nicht-Windows-Systemen entpackt werden.</span><span class="sxs-lookup"><span data-stu-id="8cd38-106">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span>  
  
 <span data-ttu-id="8cd38-107">Beim Dekomprimieren einer ZIP-Datei, die für eine frühere Version der .NET Framework-Zielplattform unter einem anderen als dem Windows-Betriebssystem – wie etwa dem Macintosh – erstellt wurde, bleibt die Verzeichnisstruktur nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="8cd38-107">Decompressing a zip file created  by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="8cd38-108">Beispielsweise wird auf dem Macintosh ein Satz Dateien erstellt, deren Dateinamen eine Verkettung aus dem Verzeichnispfad mit allen ggf. vorhandenen umgekehrten Schrägstrichzeichen („\\“) darstellen.</span><span class="sxs-lookup"><span data-stu-id="8cd38-108">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="8cd38-109">Im Ergebnis wird die Verzeichnisstruktur der dekomprimierten Dateien nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="8cd38-109">As a result, the directory structure of decompressed files is not preserved.</span></span>  
  
 <span data-ttu-id="8cd38-110">Die Auswirkungen dieser Änderungen auf ZIP-Dateien, die unter dem Windows-Betriebssystem durch die APIs im .NET Framework <xref:System.IO>-Namespace dekomprimiert werden, sollten minimal sein, da diese APIs sowohl den einfachen Schrägstrich („/“) als auch den umgekehrten Schrägstrich („\\“) als Pfadtrennzeichen verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="8cd38-110">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO> namespace should be minimal, since these APIs can seamlessly handle either a slash ("/") or a backslash ("\\") as the path separator character.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="8cd38-111">Minderung</span><span class="sxs-lookup"><span data-stu-id="8cd38-111">Mitigation</span></span>  
 <span data-ttu-id="8cd38-112">Wenn dieses Verhalten nicht erwünscht ist, können Sie sich dagegen entscheiden, indem Sie dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei eine Konfigurationseinstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8cd38-112">If this behavior is undesirable, you can opt out of by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="8cd38-113">Im Folgenden sind sowohl der Abschnitt `<runtime>` als auch der Schalter zur Ablehnung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8cd38-113">The following shows both the `<runtime>` section and the opt-out switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 <span data-ttu-id="8cd38-114">Darüber hinaus können Apps mit früheren Versionen von .NET Framework als Zielplattform, die unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und höheren Versionen ausgeführt werden, sich für die Verwendung dieses Verhaltens entscheiden, indem sie dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei eine Konfigurationseinstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8cd38-114">In addition, apps that target previous versions of the .NET Framework but are running on the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and later versions can opt in to this behavior by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="8cd38-115">Im Folgenden sind sowohl der Abschnitt `<runtime>` als auch der Schalter zur Annahme dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8cd38-115">The following shows both the `<runtime>` section and the opt-in switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8cd38-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cd38-116">See Also</span></span>  
 [<span data-ttu-id="8cd38-117">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="8cd38-117">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)  
 [<span data-ttu-id="8cd38-118">Anwendungskompatibilität in 4.6.1</span><span class="sxs-lookup"><span data-stu-id="8cd38-118">Application Compatibility in 4.6.1</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
