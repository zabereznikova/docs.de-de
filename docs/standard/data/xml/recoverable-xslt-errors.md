---
title: Wiederherstellbare XSLT-Fehler
ms.date: 03/30/2017
ms.assetid: 484929b0-fefb-4629-87ee-ebdde70ff1f8
ms.openlocfilehash: 8a77600c8cc1baf61ed21cc7a480b75dd2fde2dc
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827580"
---
# <a name="recoverable-xslt-errors"></a>Wiederherstellbare XSLT-Fehler
Im W3C-Dokument „XSL Transformations (XSLT) Version 1.0“ gibt es bestimmte Bereiche, bei denen es dem Anbieter der Implementierung freigestellt ist, wie er mit der jeweiligen Situation umgeht. Diese Bereiche werden als "freigegebene Verhaltensweisen" bezeichnet. Laut XSLT 1.0-Empfehlung, Abschnitt 7.3, "Creating Processing Instructions", liegt z. B. ein Fehler vor, wenn durch Instanziierung des Inhalts von `xsl:processing-instruction` außer Textknoten auch andere Knoten erstellt werden. Bei bestimmten Problemen gibt die Empfehlung zu XSLT 1.0 auch Maßnahmen für den Fall an, dass der Prozessor eine Wiederherstellung vom Fehler durchführt. Für das in Abschnitt 7.3 angeführte Problem empfiehlt das W3C, die Knoten einschließlich des Inhalts zu ignorieren, damit die Implementierung von diesem Fehler wiederherstellen kann.  
  
## <a name="discretionary-behaviors"></a>Freigegebene Verhaltensweisen  
 Die folgenden Tabelle enthält alle freigegebenen Verhaltensweisen, die gemäß der Empfehlung zu XSLT 1.0 zugelassen sind, und beschreibt, wie diese Verhaltensweisen von der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse behandelt werden.  
  
- Mit "Wiederherstellen" wird angegeben, dass die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse von diesem Fehler wiederherstellt. Das <xref:System.Xml.Xsl.XsltArgumentList.XsltMessageEncountered?displayProperty=nameWithType>-Objekt kann verwendet werden, um alle Ereignisse aus dem XSLT-Prozessor zu melden.  
  
- Mit "Fehler" wird angegeben, dass für diese Bedingung eine Ausnahme ausgelöst wird.  
  
- Die Abschnittsverweise finden Sie in den W3C-Dokumenten [XSL Transformations (XSLT) Version 1.0](https://www.w3.org/TR/xslt) und [XSL Transformations (XSLT) Version 1.0 Specification Errata](https://www.w3.org/1999/11/REC-xslt-19991116-errata/).  
  
|XSLT-Bedingung|Bereich|XslCompiledTransform-Verhaltensweise|  
|--------------------|-------------|-----------------------------------|  
|Ein Textknoten entspricht sowohl `xsl:strip-space` als auch `xsl:preserve-space`.|3.4|Wiederherstellen|  
|Ein Quellknoten entspricht mehreren Vorlagenregeln.|5.5|Wiederherstellen|  
|Ein Namespace-URI (Uniform Resource Identifier) ist als Alias für mehrere Namespace-URIs deklariert, die alle die gleiche Importpriorität haben.|7.1.1|Wiederherstellen|  
|Das aus einem Attributwert erstellte `name`-Attribut im `xsl:attribute` und im `xsl:element` ist kein QName.|7.1.2, 7.1.3|Fehler*|  
|Zwei Attributgruppen mit derselben Importpriorität und demselben erweiterten Namen haben ein gemeinsames Attribut, und es gibt keine andere Attributgruppe, die das gemeinsame Attribut mit demselben Namen und einer höheren Priorität enthält.|7.1.4|Wiederherstellen|  
|Hinzufügen eines Attributs zu einem Element, nachdem diesem untergeordnete Elemente hinzugefügt wurden.|7.1.3|Fehler*|  
|Erstellen eines Attributs mit dem Namen 'xmlns'.|7.1.3|Fehler*|  
|Hinzufügen eines Attributs zu einem Knoten, bei dem es sich nicht um ein Element handelt.|7.1.3|Fehler*|  
|Erstellen von anderen Knoten als Textknoten während der Instanziierung des Inhalts des `xsl:attribute`-Attributs.|7.1.3|Fehler*|  
|Das `name`-Attribut einer `xsl:processing-instruction` ergibt nicht gleichzeitig einen NCName und ein Verarbeitungsanweisungsziel.|7.3|Fehler*|  
|Bei der Instanziierung des Inhalts von `xsl:processing-instruction` werden statt Textknoten andere Knoten erstellt.|7.3|Fehler*|  
|Die Ergebnisse der Instanziierung des Inhalts von `xsl:processing-instruction` enthalten die Zeichenfolge „?>“.|7.3|Wiederherstellen|  
|Die Ergebnisse der Instanziierung des Inhalts von `xsl:processing-instruction` enthalten die Zeichenfolge "--" oder enden mit "-".|7.4|Wiederherstellen|  
|Bei den Ergebnisse der Instanziierung des Inhalts von `xsl:comment` werden statt Textknoten andere Knoten erstellt.|7.4|Fehler*|  
|Von der Vorlage innerhalb eines Variablenbindungselements wird ein Attributknoten oder ein Namespace-Knoten zurückgegeben.|11.2|Fehler*|  
|Fehler beim Abrufen der Ressource aus dem URI, der in die Dokumentfunktion übergeben wird.|12.1|Fehler|  
|Der URI-Verweis in der Dokumentfunktion enthält einen Fragmentbezeichner, und es tritt ein Fehler bei der Verarbeitung des Fragmentbezeichners auf.|12.1|Wiederherstellen*|  
|Es sind mehrere Attribute mit demselben Namen aber unterschiedlichen Werten vorhanden, die in der `xsl:output` nicht als cdata-section-Elemente mit derselben Importpriorität bezeichnet werden.|16|Wiederherstellen|  
|Die Codierung im `xsl:output`-Codierungsattribut wird vom Prozessor nicht unterstützt.|16.1|Wiederherstellen|  
|Deaktivieren des Ausgabeschutzes für einen Textknoten, der in der Ergebnisstruktur nicht für einen Textknoten verwendet wird.|16.4|Wiederherstellen*|  
|Konvertieren eines Ergebnisstrukturfragments in eine Zahl oder eine Zeichenfolge, falls das Ergebnisstrukturfragment einen Textknoten mit aktiviertem Ausgabeschutz enthält.|16.4|Wiederherstellen*|  
|Der Ausgabeschutz wird für ein Zeichen deaktiviert, das in der vom XSLT-Prozessor für die Ausgabe verwendeten Codierung nicht dargestellt werden kann.|16.4|Wiederherstellen*|  
|Hinzufügen eines Namespace-Knotens zu einem Element, nachdem diesem entweder untergeordnete Elemente oder Attribute hinzugefügt worden sind.|errata 25|Fehler*|  
|Das `value`-Attribut einer `xsl:number` ist NAN (Not a Number), unendlich oder kleiner als 0,5.|errata 24|Wiederherstellen|  
|Das zweite node-set-Argument der Dokumentfunktion ist leer, und der URI-Verweis ist relativ.|errata 14|Wiederherstellen|  
  
 <sup>*</sup> Diese Verhaltensweise unterscheidet sich von der der <xref:System.Xml.Xsl.XslTransform>-Klasse. Weitere Informationen finden Sie unter [Implementierung von freigegebenen Verhaltensweisen in der XslTransform-Klasse](implementation-of-discretionary-behaviors-in-the-xsltransform-class.md).  
  
## <a name="see-also"></a>Siehe auch

- [XSLT Transformations (XSLT-Transformationen)](xslt-transformations.md)
