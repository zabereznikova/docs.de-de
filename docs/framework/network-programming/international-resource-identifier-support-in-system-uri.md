---
title: International Resource Identifier-Unterstützung in System.Uri
ms.date: 03/30/2017
ms.assetid: b5e994c3-3535-4aff-8e1b-b69be22e9a22
ms.openlocfilehash: a3670c40a7a78e2ac8b521a4cb95477381848f36
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253361"
---
# <a name="international-resource-identifier-support-in-systemuri"></a>International Resource Identifier-Unterstützung in System.Uri

Die Klasse <xref:System.Uri?displayProperty=nameWithType> wurde um die Unterstützung von International Resource Identifier (IRI) und von internationalen Domänennamen (IDN) erweitert. Diese Erweiterungen sind in .NET Framework 3.5, 3.0 SP1 und 2.0 SP1 verfügbar.  
  
## <a name="iri-and-idn-support"></a>IRI- und IDN-Unterstützung  

 Webadressen werden in der Regel mithilfe von Uniform Resource Identifiers (URI) ausgedrückt, die aus einem sehr eingeschränkten Satz von Zeichen bestehen:  
  
- ASCII-Großbuchstaben und -Kleinbuchstaben des englischen Alphabets  
  
- Ziffern von 0 bis 9  
  
- einer kleinen Anzahl weiterer ASCII-Symbole  
  
 Die URI-Spezifikationen werden in RFC 2396 und RFC 3986 dokumentiert, die von der Internet Engineering Task Force (IETF) veröffentlicht werden.  
  
 Durch das ständige Wachstum des Internets wird es immer notwendiger, Ressourcen in anderen Sprachen als in Englisch zu bezeichnen. Bezeichner, die dies ermöglichen und die Nicht-ASCII-Zeichen (Zeichen des Unicode-/ISO-Zeichensatzes 10646) zulassen, werden als International Resource Identifiers (IRIs) bezeichnet. Die IRI-Spezifikationen werden in RFC 3987 dokumentiert, die von der IETF veröffentlicht wird. Wenn IRIs verwendet werden, kann eine URL Unicode-Zeichen enthalten.  
  
 Die vorhandene Klasse <xref:System.Uri?displayProperty=nameWithType> wurde erweitert und stellt nun IRI-Unterstützung basierend auf RFC 3987 bereit. Derzeitige Benutzer werden keine Änderung gegenüber dem .NET Framework 2.0-Verhalten feststellen, außer IRI wird explizit aktiviert. Dadurch wird die Anwendungskompatibilität mit früheren Versionen von .NET Framework garantiert.  
  
 In einer Anwendung kann angegeben werden, ob die IDN-Analyse auf Domänennamen angewendet werden soll und ob IRI-Analyseregeln anzuwenden sind. Dies kann in der Datei „machine.config“ oder in der Datei „App.config“ durchgeführt werden.  
  
 Beim Aktivieren von IDN werden alle Unicode-Bezeichnungen in einem Domänennamen in ihre Punycode-Entsprechungen konvertiert. Punycode-Namen enthalten nur ASCII-Zeichen und beginnen immer mit dem Präfix „xn--“. So werden vorhandene DNS-Server im Internet unterstützt, da die meisten DNS-Server nur ASCII-Zeichen unterstützen (siehe RFC 3940).  
  
 Das Aktivieren von IRI und IDN wirkt sich auf den Wert der Eigenschaft <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType> aus. Das Aktivieren von IRI und IDN kann auch das Verhalten der Methoden <xref:System.Uri.Equals%2A?displayProperty=nameWithType>, <xref:System.Uri.OriginalString%2A?displayProperty=nameWithType>, <xref:System.Uri.GetComponents%2A?displayProperty=nameWithType> und <xref:System.Uri.IsWellFormedOriginalString%2A> verändern.  
  
 Die Klasse <xref:System.GenericUriParser?displayProperty=nameWithType> wurde ebenfalls erweitert, um das Erstellen eines anpassbaren Parsers zu ermöglichen, der IRI und IDN unterstützt. Das Verhalten eines <xref:System.GenericUriParser?displayProperty=nameWithType>-Objekts wird durch Übergabe einer bitweisen Kombination von Werten angegeben, die in der <xref:System.GenericUriParserOptions?displayProperty=nameWithType>-Enumeration des <xref:System.GenericUriParser?displayProperty=nameWithType>-Konstruktors verfügbar sind. Der <xref:System.GenericUriParserOptions.IriParsing?displayProperty=nameWithType>-Typ gibt an, dass der Parser die in RFC 3987 angegebenen Analyseregeln für International Resource Identifiers (IRI) unterstützt. Ob IRI auch tatsächlich verwendet wird, hängt davon ab, ob es aktiviert ist.  
  
 Der <xref:System.GenericUriParserOptions.Idn?displayProperty=nameWithType>-Typ gibt an, dass der Parser die IDN-Analyse von Hostnamen unterstützt. Ob IDN auch tatsächlich verwendet wird, hängt davon ab, ob es aktiviert ist.  
  
 Durch Aktivieren der IRI-Analyse wird die Normalisierung und Zeichenüberprüfung gemäß den neuesten IRI-Regeln in RFC 3987 ausgeführt. Standardmäßig ist die IRI-Analyse deaktiviert, sodass die Normalisierung und Zeichenüberprüfung gemäß RFC 2396 und RFC 3986 durchgeführt wird.  
  
 Die Verarbeitung von IRI und IDN in der Klasse <xref:System.Uri?displayProperty=nameWithType> kann auch mithilfe der Konfigurationseinstellungsklassen <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> und <xref:System.Configuration.IdnElement?displayProperty=nameWithType> gesteuert werden. Die Einstellung <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> aktiviert oder deaktiviert die IRI-Verarbeitung in der Klasse <xref:System.Uri?displayProperty=nameWithType>. Die Einstellung <xref:System.Configuration.IdnElement?displayProperty=nameWithType> aktiviert oder deaktiviert die IDN-Verarbeitung in der Klasse <xref:System.Uri>. Die Einstellung <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> steuert indirekt auch IDN. Die IRI-Verarbeitung muss aktiviert werden, damit die IDN-Verarbeitung überhaupt möglich ist. Ist die IRI-Verarbeitung deaktiviert, wird die IDN-Verarbeitung auf die Standardeinstellung festgelegt. Darin wird aus Kompatibilitätsgründen das .NET Framework 2.0-Verhalten verwendet, und IDN-Namen werden nicht verwendet.  
  
 Die Konfigurationseinstellung für die Konfigurationsklassen <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> und <xref:System.Configuration.IdnElement?displayProperty=nameWithType> wird beim Erstellen der ersten Klasse <xref:System.Uri?displayProperty=nameWithType> einmal gelesen. Später vorgenommene Änderungen an den Konfigurationseinstellungen werden anschließend ignoriert.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType>
