---
title: Änderungen am System.Uri-Namespace in Version 2.0
ms.date: 03/30/2017
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
ms.openlocfilehash: 987010b8367069e8089df3f809d23f258bb68f2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "61642762"
---
# <a name="changes-to-the-systemuri-namespace-in-version-20"></a>Änderungen am System.Uri-Namespace in Version 2.0

Es wurden mehrere Änderungen an der <xref:System.Uri?displayProperty=nameWithType>-Klasse vorgenommen. Diese Änderungen korrigierten falsches Verhalten, verbesserten die Verwendbarkeit und Sicherheit.

## <a name="obsolete-and-deprecated-members"></a>Veraltete Member

 Konstruktoren:

- Alle Konstruktoren, die über einen `dontEscape`-Parameter verfügen.

 Methoden:

- <xref:System.Uri.CheckSecurity%2A>

- <xref:System.Uri.Escape%2A>

- <xref:System.Uri.Canonicalize%2A>

- <xref:System.Uri.Parse%2A>

- <xref:System.Uri.IsReservedCharacter%2A>

- <xref:System.Uri.IsBadFileSystemCharacter%2A>

- <xref:System.Uri.IsExcludedCharacter%2A>

- <xref:System.Uri.EscapeString%2A>

## <a name="changes"></a>Änderungen

- Für URI-Schemas, die bekanntermaßen nicht zwingend über einen Abfrageteil (Datei, ftp usw.) verfügen, ist das „?“-Zeichen immer mit Leerzeichen versehen und wird nicht als Anfang des <xref:System.Uri.Query%2A>-Teils angesehen.

- Für implizite URI-Dateien (im Format `c:\directory\file@name.txt`) wird das Fragmentzeichen („#“) immer mit einem Leerzeichen versehen, außer die Funktion für die Entfernung der Escapezeichen wird angefordert, oder <xref:System.Uri.LocalPath%2A> entspricht `true`.

- Die Unterstützung des UNC-Hostnames wurde entfernt. Die IDN-Spezifikation für die Darstellung internationaler Hostnamen wurde übernommen.

- <xref:System.Uri.LocalPath%2A> gibt immer eine Zeichenfolge ohne Escapezeichen zurück.

- <xref:System.Uri.ToString%2A> verwendet die Funktion für die Entfernung der Escapezeichen nicht, um ein Escapezeichen vom Typ „%“, „?“ oder „#“ zu entfernen.

- <xref:System.Uri.Equals%2A> enthält jetzt den <xref:System.Uri.Query%2A>-Teil in der Gleichheitsüberprüfung.

- Die Operatoren „==“ und „! =“ werden überschrieben und mit der <xref:System.Uri.Equals%2A>-Methode verknüpft.

- <xref:System.Uri.IsLoopback%2A> erzeugt jetzt konsistente Ergebnisse.

- Der URI „`file:///path`“ wird nicht mehr in `file://path` übersetzt.

- „#“ wird nun als Abschlusszeichen eines Hostnamen erkannt werden. D.h.: `http://contoso.com#fragment` wird jetzt in `http://contoso.com/#fragment` konvertiert.

- Ein Fehler bei der Kombination eines Basis-URI mit einem Fragment wurde behoben.

- Ein Fehler in <xref:System.Uri.HostNameType%2A> wurde behoben.

- Ein Fehler beim Analysieren von NNTP wurde behoben.

- Der URI des Formulars HTTP:contoso.com löst nun eine Ausnahme bei der Analyse aus.

- Das Framework verarbeitet die Benutzerinformationen in einem URI ordnungsgemäß.

- Die URI-Pfadkomprimierung wird repariert, sodass ein fehlerhafter URI das Dateisystem oberhalb des Stammverzeichnisses nicht durchlaufen kann.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Uri?displayProperty=nameWithType>
