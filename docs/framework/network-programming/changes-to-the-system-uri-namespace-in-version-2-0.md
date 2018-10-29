---
title: Änderungen am System.Uri-Namespace in Version 2.0
ms.date: 03/30/2017
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
ms.openlocfilehash: 987010b8367069e8089df3f809d23f258bb68f2b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188432"
---
# <a name="changes-to-the-systemuri-namespace-in-version-20"></a><span data-ttu-id="6780f-102">Änderungen am System.Uri-Namespace in Version 2.0</span><span class="sxs-lookup"><span data-stu-id="6780f-102">Changes to the System.Uri namespace in version 2.0</span></span>

<span data-ttu-id="6780f-103">Es wurden mehrere Änderungen an der <xref:System.Uri?displayProperty=nameWithType>-Klasse vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="6780f-103">Several changes were made to the <xref:System.Uri?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="6780f-104">Diese Änderungen korrigierten falsches Verhalten, verbesserten die Verwendbarkeit und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="6780f-104">These changes fixed incorrect behavior, enhanced usability, and enhanced security.</span></span>

## <a name="obsolete-and-deprecated-members"></a><span data-ttu-id="6780f-105">Veraltete Member</span><span class="sxs-lookup"><span data-stu-id="6780f-105">Obsolete and deprecated Members</span></span>

 <span data-ttu-id="6780f-106">Konstruktoren:</span><span class="sxs-lookup"><span data-stu-id="6780f-106">Constructors:</span></span>

- <span data-ttu-id="6780f-107">Alle Konstruktoren, die über einen `dontEscape`-Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="6780f-107">All constructors that have a `dontEscape` parameter.</span></span>

 <span data-ttu-id="6780f-108">Methoden:</span><span class="sxs-lookup"><span data-stu-id="6780f-108">Methods:</span></span>

- <xref:System.Uri.CheckSecurity%2A>

- <xref:System.Uri.Escape%2A>

- <xref:System.Uri.Canonicalize%2A>

- <xref:System.Uri.Parse%2A>

- <xref:System.Uri.IsReservedCharacter%2A>

- <xref:System.Uri.IsBadFileSystemCharacter%2A>

- <xref:System.Uri.IsExcludedCharacter%2A>

- <xref:System.Uri.EscapeString%2A>

## <a name="changes"></a><span data-ttu-id="6780f-109">Änderungen</span><span class="sxs-lookup"><span data-stu-id="6780f-109">Changes</span></span>

- <span data-ttu-id="6780f-110">Für URI-Schemas, die bekanntermaßen nicht zwingend über einen Abfrageteil (Datei, ftp usw.) verfügen, ist das „?“-Zeichen immer mit Leerzeichen versehen und wird nicht als Anfang des <xref:System.Uri.Query%2A>-Teils angesehen.</span><span class="sxs-lookup"><span data-stu-id="6780f-110">For URI schemes that are known to not have a query part (file, ftp, and others), the '?' character is always escaped and is not considered the beginning of a <xref:System.Uri.Query%2A> part.</span></span>

- <span data-ttu-id="6780f-111">Für implizite URI-Dateien (im Format `c:\directory\file@name.txt`) wird das Fragmentzeichen („#“) immer mit einem Leerzeichen versehen, außer die Funktion für die Entfernung der Escapezeichen wird angefordert, oder <xref:System.Uri.LocalPath%2A> entspricht `true`.</span><span class="sxs-lookup"><span data-stu-id="6780f-111">For implicit file URIs (of the form `c:\directory\file@name.txt`), the fragment character ('#') is always escaped unless full unescaping is requested or <xref:System.Uri.LocalPath%2A> is `true`.</span></span>

- <span data-ttu-id="6780f-112">Die Unterstützung des UNC-Hostnames wurde entfernt. Die IDN-Spezifikation für die Darstellung internationaler Hostnamen wurde übernommen.</span><span class="sxs-lookup"><span data-stu-id="6780f-112">UNC hostname support was removed; the IDN specification for representing international hostnames was adopted.</span></span>

- <span data-ttu-id="6780f-113"><xref:System.Uri.LocalPath%2A> gibt immer eine Zeichenfolge ohne Escapezeichen zurück.</span><span class="sxs-lookup"><span data-stu-id="6780f-113"><xref:System.Uri.LocalPath%2A> always returns a completely unescaped string.</span></span>

- <span data-ttu-id="6780f-114"><xref:System.Uri.ToString%2A> verwendet die Funktion für die Entfernung der Escapezeichen nicht, um ein Escapezeichen vom Typ „%“, „?“ oder „#“ zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6780f-114"><xref:System.Uri.ToString%2A> does not unescape an escaped '%', '?', or '#' character.</span></span>

- <span data-ttu-id="6780f-115"><xref:System.Uri.Equals%2A> enthält jetzt den <xref:System.Uri.Query%2A>-Teil in der Gleichheitsüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="6780f-115"><xref:System.Uri.Equals%2A> now includes the <xref:System.Uri.Query%2A> part in the equality check.</span></span>

- <span data-ttu-id="6780f-116">Die Operatoren „==“ und „! =“ werden überschrieben und mit der <xref:System.Uri.Equals%2A>-Methode verknüpft.</span><span class="sxs-lookup"><span data-stu-id="6780f-116">Operators "==" and "!=" are overridden and linked to the <xref:System.Uri.Equals%2A> method.</span></span>

- <span data-ttu-id="6780f-117"><xref:System.Uri.IsLoopback%2A> erzeugt jetzt konsistente Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="6780f-117"><xref:System.Uri.IsLoopback%2A> now produces consistent results.</span></span>

- <span data-ttu-id="6780f-118">Der URI „`file:///path`“ wird nicht mehr in `file://path` übersetzt.</span><span class="sxs-lookup"><span data-stu-id="6780f-118">The URI "`file:///path`" is no longer translated into `file://path`.</span></span>

- <span data-ttu-id="6780f-119">„#“ wird nun als Abschlusszeichen eines Hostnamen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="6780f-119">"#" is now recognized as a host name terminator.</span></span> <span data-ttu-id="6780f-120">D.h.: `http://contoso.com#fragment` wird jetzt in `http://contoso.com/#fragment` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="6780f-120">That is, `http://contoso.com#fragment` is now converted to `http://contoso.com/#fragment`.</span></span>

- <span data-ttu-id="6780f-121">Ein Fehler bei der Kombination eines Basis-URI mit einem Fragment wurde behoben.</span><span class="sxs-lookup"><span data-stu-id="6780f-121">A bug when combining a base URI with a fragment has been fixed.</span></span>

- <span data-ttu-id="6780f-122">Ein Fehler in <xref:System.Uri.HostNameType%2A> wurde behoben.</span><span class="sxs-lookup"><span data-stu-id="6780f-122">A bug in <xref:System.Uri.HostNameType%2A> is fixed.</span></span>

- <span data-ttu-id="6780f-123">Ein Fehler beim Analysieren von NNTP wurde behoben.</span><span class="sxs-lookup"><span data-stu-id="6780f-123">A bug in NNTP parsing is fixed.</span></span>

- <span data-ttu-id="6780f-124">Der URI des Formulars HTTP:contoso.com löst nun eine Ausnahme bei der Analyse aus.</span><span class="sxs-lookup"><span data-stu-id="6780f-124">A URI of the form HTTP:contoso.com now throws a parsing exception.</span></span>

- <span data-ttu-id="6780f-125">Das Framework verarbeitet die Benutzerinformationen in einem URI ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="6780f-125">The Framework correctly handles userinfo in a URI.</span></span>

- <span data-ttu-id="6780f-126">Die URI-Pfadkomprimierung wird repariert, sodass ein fehlerhafter URI das Dateisystem oberhalb des Stammverzeichnisses nicht durchlaufen kann.</span><span class="sxs-lookup"><span data-stu-id="6780f-126">URI path compression is fixed so that a broken URI cannot traverse the file system above the root.</span></span>

## <a name="see-also"></a><span data-ttu-id="6780f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6780f-127">See also</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
