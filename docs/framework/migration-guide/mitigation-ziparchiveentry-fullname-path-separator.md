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
ms.openlocfilehash: 021d22e90ba39a4d01cf7d64588fab2d724b6640
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457731"
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a><span data-ttu-id="376ef-102">Entschärfung: Pfadtrennzeichen für ZipArchiveEntry.FullName</span><span class="sxs-lookup"><span data-stu-id="376ef-102">Mitigation: ZipArchiveEntry.FullName Path Separator</span></span>
<span data-ttu-id="376ef-103">Beginnend mit Apps, die gezielt .NET Framework 4.6.1 verwenden, ändert sich das in der Eigenschaft <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> verwendete Pfadtrennzeichen von einem umgekehrten Schrägstrich (\\) aus den Vorgängerversionen von .NET Framework in einen einfachen Schrägstrich (/).</span><span class="sxs-lookup"><span data-stu-id="376ef-103">Starting with apps that target the .NET Framework 4.6.1, the path separator used in the <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> property has changed from the backslash ("\\") used in previous versions of the .NET Framework to a forward slash ("/").</span></span>   <span data-ttu-id="376ef-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType>-Objekte werden durch Aufrufen einer der Überladungen der <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>-Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="376ef-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> objects are created by calling one of the overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="376ef-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="376ef-105">Impact</span></span>  
 <span data-ttu-id="376ef-106">Die Änderung bringt die .NET-Implementierung in Einklang mit Abschnitt 4.4.17.1 der [ZIP-Dateiformatspezifikation](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) und ermöglicht es, dass ZIP-Archive auf Nicht-Windows-Systemen entpackt werden.</span><span class="sxs-lookup"><span data-stu-id="376ef-106">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span>  
  
 <span data-ttu-id="376ef-107">Beim Dekomprimieren einer ZIP-Datei, die für eine frühere Version der .NET Framework-Zielplattform unter einem anderen als dem Windows-Betriebssystem – wie etwa dem Macintosh – erstellt wurde, bleibt die Verzeichnisstruktur nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="376ef-107">Decompressing a zip file created  by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="376ef-108">Beispielsweise wird auf dem Macintosh ein Satz Dateien erstellt, deren Dateinamen eine Verkettung aus dem Verzeichnispfad mit allen ggf. vorhandenen umgekehrten Schrägstrichzeichen („\\“) darstellen.</span><span class="sxs-lookup"><span data-stu-id="376ef-108">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="376ef-109">Im Ergebnis wird die Verzeichnisstruktur der dekomprimierten Dateien nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="376ef-109">As a result, the directory structure of decompressed files is not preserved.</span></span>  
  
 <span data-ttu-id="376ef-110">Die Auswirkungen dieser Änderungen auf ZIP-Dateien, die unter dem Windows-Betriebssystem durch die APIs im .NET Framework <xref:System.IO>-Namespace dekomprimiert werden, sollten minimal sein, da diese APIs sowohl den einfachen Schrägstrich („/“) als auch den umgekehrten Schrägstrich („\\“) als Pfadtrennzeichen verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="376ef-110">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO> namespace should be minimal, since these APIs can seamlessly handle either a slash ("/") or a backslash ("\\") as the path separator character.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="376ef-111">Minderung</span><span class="sxs-lookup"><span data-stu-id="376ef-111">Mitigation</span></span>  
 <span data-ttu-id="376ef-112">Wenn dieses Verhalten nicht erwünscht ist, können Sie sich dagegen entscheiden, indem Sie dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei eine Konfigurationseinstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="376ef-112">If this behavior is undesirable, you can opt out of by adding a configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="376ef-113">Im Folgenden sind sowohl der Abschnitt `<runtime>` als auch der Schalter zur Ablehnung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="376ef-113">The following shows both the `<runtime>` section and the opt-out switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 <span data-ttu-id="376ef-114">Darüber hinaus kann für Apps mit früheren Versionen von .NET Framework als Zielplattform, die unter .NET Framework 4.6.1 und neueren Versionen ausgeführt werden, die Verwendung dieses Verhaltens akzeptiert werden, indem Sie dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei eine Konfigurationseinstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="376ef-114">In addition, apps that target previous versions of the .NET Framework but are running on the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding a configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="376ef-115">Im Folgenden sind sowohl der Abschnitt `<runtime>` als auch der Schalter zur Annahme dargestellt.</span><span class="sxs-lookup"><span data-stu-id="376ef-115">The following shows both the `<runtime>` section and the opt-in switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="376ef-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="376ef-116">See also</span></span>

- [<span data-ttu-id="376ef-117">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="376ef-117">Retargeting Changes</span></span>](retargeting-changes-in-the-net-framework-4-6-1.md)
- [<span data-ttu-id="376ef-118">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="376ef-118">Application compatibility</span></span>](application-compatibility.md)
