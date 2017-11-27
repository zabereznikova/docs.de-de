---
title: "Änderungen am System.Uri-Namespace in Version 2.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 906abbcbd3ec00e76d8c183f61828fb5135d9154
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="changes-to-the-systemuri-namespace-in-version-20"></a><span data-ttu-id="e7a29-102">Änderungen am System.Uri-Namespace in Version 2.0</span><span class="sxs-lookup"><span data-stu-id="e7a29-102">Changes to the System.Uri namespace in Version 2.0</span></span>
<span data-ttu-id="e7a29-103">Es wurden mehrere Änderungen an der <xref:System.Uri?displayProperty=nameWithType>-Klasse vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="e7a29-103">Several changes were made to the <xref:System.Uri?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="e7a29-104">Diese Änderungen korrigierten falsches Verhalten, verbesserten die Verwendbarkeit und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="e7a29-104">These changes fixed incorrect behavior, enhanced usability, and enhanced security.</span></span>  
  
## <a name="obsolete-and-deprecated-members"></a><span data-ttu-id="e7a29-105">Veraltete Member</span><span class="sxs-lookup"><span data-stu-id="e7a29-105">Obsolete and Deprecated Members</span></span>  
 <span data-ttu-id="e7a29-106">Konstruktoren:</span><span class="sxs-lookup"><span data-stu-id="e7a29-106">Constructors:</span></span>  
  
-   <span data-ttu-id="e7a29-107">Alle Konstruktoren, die über einen `dontEscape`-Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="e7a29-107">All constructors that have a `dontEscape` parameter.</span></span>  
  
 <span data-ttu-id="e7a29-108">Methoden:</span><span class="sxs-lookup"><span data-stu-id="e7a29-108">Methods:</span></span>  
  
-   <xref:System.Uri.CheckSecurity%2A>  
  
-   <xref:System.Uri.Escape%2A>  
  
-   <xref:System.Uri.Canonicalize%2A>  
  
-   <xref:System.Uri.Parse%2A>  
  
-   <xref:System.Uri.IsReservedCharacter%2A>  
  
-   <xref:System.Uri.IsBadFileSystemCharacter%2A>  
  
-   <xref:System.Uri.IsExcludedCharacter%2A>  
  
-   <xref:System.Uri.EscapeString%2A>  
  
## <a name="changes"></a><span data-ttu-id="e7a29-109">Änderungen</span><span class="sxs-lookup"><span data-stu-id="e7a29-109">Changes</span></span>  
  
-   <span data-ttu-id="e7a29-110">Für URI-Schemas, die bekanntermaßen nicht zwingend über einen Abfrageteil (Datei, ftp usw.) verfügen, ist das „?“-Zeichen immer mit Leerzeichen versehen und wird nicht als Anfang des <xref:System.Uri.Query%2A>-Teils angesehen.</span><span class="sxs-lookup"><span data-stu-id="e7a29-110">For URI schemes that are known to not have a query part (file, ftp, and others), the '?' character is always escaped and is not considered the beginning of a <xref:System.Uri.Query%2A> part.</span></span>  
  
-   <span data-ttu-id="e7a29-111">Für implizite URI-Dateien (im Format „c:\directory\file@name.txt“) wird das Fragmentzeichen („#“) immer mit einem Leerzeichen versehen, außer die Funktion für die Entfernung der Escapezeichen wird angefordert, oder <xref:System.Uri.LocalPath%2A> entspricht `true`.</span><span class="sxs-lookup"><span data-stu-id="e7a29-111">For implicit file URIs (of the form "c:\directory\file@name.txt"), the fragment character ('#') is always escaped unless full unescaping is requested or <xref:System.Uri.LocalPath%2A> is `true`.</span></span>  
  
-   <span data-ttu-id="e7a29-112">Die Unterstützung des UNC-Hostnames wurde entfernt. Die IDN-Spezifikation für die Darstellung internationaler Hostnamen wurde übernommen.</span><span class="sxs-lookup"><span data-stu-id="e7a29-112">UNC hostname support was removed; the IDN specification for representing international hostnames was adopted.</span></span>  
  
-   <span data-ttu-id="e7a29-113"><xref:System.Uri.LocalPath%2A> gibt immer eine Zeichenfolge ohne Escapezeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="e7a29-113"><xref:System.Uri.LocalPath%2A> always returns a completely unescaped string.</span></span>  
  
-   <span data-ttu-id="e7a29-114"><xref:System.Uri.ToString%2A> verwendet die Funktion für die Entfernung der Escapezeichen nicht, um ein Escapezeichen vom Typ „%“, „?“ oder „#“ zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e7a29-114"><xref:System.Uri.ToString%2A> does not unescape an escaped '%', '?', or '#' character.</span></span>  
  
-   <span data-ttu-id="e7a29-115"><xref:System.Uri.Equals%2A> enthält jetzt den <xref:System.Uri.Query%2A>-Teil in der Gleichheitsüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="e7a29-115"><xref:System.Uri.Equals%2A> now includes the <xref:System.Uri.Query%2A> part in the equality check.</span></span>  
  
-   <span data-ttu-id="e7a29-116">Die Operatoren „==“ und „! =“ werden überschrieben und mit der <xref:System.Uri.Equals%2A>-Methode verknüpft.</span><span class="sxs-lookup"><span data-stu-id="e7a29-116">Operators "==" and "!=" are overridden and linked to the <xref:System.Uri.Equals%2A> method.</span></span>  
  
-   <span data-ttu-id="e7a29-117"><xref:System.Uri.IsLoopback%2A> erzeugt jetzt konsistente Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="e7a29-117"><xref:System.Uri.IsLoopback%2A> now produces consistent results.</span></span>  
  
-   <span data-ttu-id="e7a29-118">Der URI „`file:///path`“ wird nicht mehr in „file://path“ übersetzt.</span><span class="sxs-lookup"><span data-stu-id="e7a29-118">The URI "`file:///path`" is no longer translated into "file://path".</span></span>  
  
-   <span data-ttu-id="e7a29-119">„#“ wird nun als Abschlusszeichen eines Hostnamen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="e7a29-119">"#" is now recognized as a host name terminator.</span></span> <span data-ttu-id="e7a29-120">D.h., „http://consoto.com#fragment“ wird jetzt in „http://contoso.com/#fragment“ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e7a29-120">That is, "http://consoto.com#fragment" is now converted to "http://contoso.com/#fragment".</span></span>  
  
-   <span data-ttu-id="e7a29-121">Ein Fehler bei der Kombination eines Basis-URI mit einem Fragment wurde behoben.</span><span class="sxs-lookup"><span data-stu-id="e7a29-121">A bug when combining a base URI with a fragment has been fixed.</span></span>  
  
-   <span data-ttu-id="e7a29-122">Ein Fehler in <xref:System.Uri.HostNameType%2A> wurde behoben.</span><span class="sxs-lookup"><span data-stu-id="e7a29-122">A bug in <xref:System.Uri.HostNameType%2A> is fixed.</span></span>  
  
-   <span data-ttu-id="e7a29-123">Ein Fehler beim Analysieren von NNTP wurde behoben.</span><span class="sxs-lookup"><span data-stu-id="e7a29-123">A bug in NNTP parsing is fixed.</span></span>  
  
-   <span data-ttu-id="e7a29-124">Der URI des Formulars HTTP:contoso.com löst nun eine Ausnahme bei der Analyse aus.</span><span class="sxs-lookup"><span data-stu-id="e7a29-124">A URI of the form HTTP:contoso.com now throws a parsing exception.</span></span>  
  
-   <span data-ttu-id="e7a29-125">Das Framework verarbeitet die Benutzerinformationen in einem URI ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="e7a29-125">The Framework correctly handles userinfo in a URI.</span></span>  
  
-   <span data-ttu-id="e7a29-126">Die URI-Pfadkomprimierung wird repariert, sodass ein fehlerhafter URI das Dateisystem oberhalb des Stammverzeichnisses nicht durchlaufen kann.</span><span class="sxs-lookup"><span data-stu-id="e7a29-126">URI path compression is fixed so that a broken URI cannot traverse the file system above the root.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a29-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7a29-127">See Also</span></span>  
 <xref:System.Uri?displayProperty=nameWithType>
