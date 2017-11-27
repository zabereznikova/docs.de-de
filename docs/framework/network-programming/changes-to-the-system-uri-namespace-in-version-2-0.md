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
# <a name="changes-to-the-systemuri-namespace-in-version-20"></a>Änderungen am System.Uri-Namespace in Version 2.0
Es wurden mehrere Änderungen an der <xref:System.Uri?displayProperty=nameWithType>-Klasse vorgenommen. Diese Änderungen korrigierten falsches Verhalten, verbesserten die Verwendbarkeit und Sicherheit.  
  
## <a name="obsolete-and-deprecated-members"></a>Veraltete Member  
 Konstruktoren:  
  
-   Alle Konstruktoren, die über einen `dontEscape`-Parameter verfügen.  
  
 Methoden:  
  
-   <xref:System.Uri.CheckSecurity%2A>  
  
-   <xref:System.Uri.Escape%2A>  
  
-   <xref:System.Uri.Canonicalize%2A>  
  
-   <xref:System.Uri.Parse%2A>  
  
-   <xref:System.Uri.IsReservedCharacter%2A>  
  
-   <xref:System.Uri.IsBadFileSystemCharacter%2A>  
  
-   <xref:System.Uri.IsExcludedCharacter%2A>  
  
-   <xref:System.Uri.EscapeString%2A>  
  
## <a name="changes"></a>Änderungen  
  
-   Für URI-Schemas, die bekanntermaßen nicht zwingend über einen Abfrageteil (Datei, ftp usw.) verfügen, ist das „?“-Zeichen immer mit Leerzeichen versehen und wird nicht als Anfang des <xref:System.Uri.Query%2A>-Teils angesehen.  
  
-   Für implizite URI-Dateien (im Format „c:\directory\file@name.txt“) wird das Fragmentzeichen („#“) immer mit einem Leerzeichen versehen, außer die Funktion für die Entfernung der Escapezeichen wird angefordert, oder <xref:System.Uri.LocalPath%2A> entspricht `true`.  
  
-   Die Unterstützung des UNC-Hostnames wurde entfernt. Die IDN-Spezifikation für die Darstellung internationaler Hostnamen wurde übernommen.  
  
-   <xref:System.Uri.LocalPath%2A> gibt immer eine Zeichenfolge ohne Escapezeichen zurück.  
  
-   <xref:System.Uri.ToString%2A> verwendet die Funktion für die Entfernung der Escapezeichen nicht, um ein Escapezeichen vom Typ „%“, „?“ oder „#“ zu entfernen.  
  
-   <xref:System.Uri.Equals%2A> enthält jetzt den <xref:System.Uri.Query%2A>-Teil in der Gleichheitsüberprüfung.  
  
-   Die Operatoren „==“ und „! =“ werden überschrieben und mit der <xref:System.Uri.Equals%2A>-Methode verknüpft.  
  
-   <xref:System.Uri.IsLoopback%2A> erzeugt jetzt konsistente Ergebnisse.  
  
-   Der URI „`file:///path`“ wird nicht mehr in „file://path“ übersetzt.  
  
-   „#“ wird nun als Abschlusszeichen eines Hostnamen erkannt werden. D.h., „http://consoto.com#fragment“ wird jetzt in „http://contoso.com/#fragment“ konvertiert.  
  
-   Ein Fehler bei der Kombination eines Basis-URI mit einem Fragment wurde behoben.  
  
-   Ein Fehler in <xref:System.Uri.HostNameType%2A> wurde behoben.  
  
-   Ein Fehler beim Analysieren von NNTP wurde behoben.  
  
-   Der URI des Formulars HTTP:contoso.com löst nun eine Ausnahme bei der Analyse aus.  
  
-   Das Framework verarbeitet die Benutzerinformationen in einem URI ordnungsgemäß.  
  
-   Die URI-Pfadkomprimierung wird repariert, sodass ein fehlerhafter URI das Dateisystem oberhalb des Stammverzeichnisses nicht durchlaufen kann.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Uri?displayProperty=nameWithType>
