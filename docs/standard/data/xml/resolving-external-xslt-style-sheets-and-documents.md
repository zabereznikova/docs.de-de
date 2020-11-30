---
title: Auflösen von externen XSLT-Stylesheets und Dokumenten
ms.date: 03/30/2017
ms.assetid: 920cfe3b-d525-4bb2-abf6-9431651f9cf9
ms.openlocfilehash: f1fbf950f7d67d46937652987516e5faf9857b85
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686565"
---
# <a name="resolving-external-xslt-style-sheets-and-documents"></a>Auflösen von externen XSLT-Stylesheets und Dokumenten

Während einer Transformation müssen Sie u. U. mehrmals externe Ressourcen auflösen.  
  
> [!NOTE]
> Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen.  
  
 Während einer Transformation müssen Sie u. U. mehrmals externe Ressourcen auflösen:  
  
- Während <xref:System.Xml.Xsl.XslTransform.Load%2A> ausgeführt wird, um ein externes Stylesheet zu suchen.  
  
- Während <xref:System.Xml.Xsl.XslTransform.Load%2A> ausgeführt wird, um ein beliebiges `<xsl:include>`-Element oder ein beliebiges `<xsl:import>`-Element im Stylesheet aufzulösen.  
  
- Während <xref:System.Xml.Xsl.XslTransform.Transform%2A> ausgeführt wird, um eine beliebige `document()`-Funktion aufzulösen.  
  
## <a name="using-the-xmlresolver-class"></a>Verwenden der XmlResolver-Klasse  

 Wenn für den Zugriff auf eine Netzwerkressource eine Authentifizierung erforderlich ist, verwenden Sie die <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methoden, die über einen <xref:System.Xml.XmlResolver>-Parameter verfügen, um das <xref:System.Xml.XmlResolver>-Objekt zu übergeben, bei dem die notwendigen Anmeldeeigenschaften festgelegt sind.  
  
 Wenn Sie einen benutzerdefinierten <xref:System.Xml.XmlResolver> verwenden möchten, oder wenn Sie abweichende Anmeldeinformationen angeben müssen, finden Sie in der nachfolgenden Tabelle die erforderliche Vorgehensweise, je nach dem für das Auflösen der externen Ressource erforderlichen Zeitpunkt.  
  
|Aufzulösender Prozess|Erforderliche Vorgehensweise|  
|--------------------------------------|-------------------|  
|Während <xref:System.Xml.Xsl.XslTransform.Load%2A> ausgeführt wird, um das Stylesheet zu suchen.|Geben Sie die Überladung der <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode an, die einen <xref:System.Xml.XmlResolver> als Parameter annimmt, wenn sich das Stylesheet in einer Ressource befindet, die Anmeldeinformationen erfordert.|  
|Während <xref:System.Xml.Xsl.XslTransform.Load%2A> ausgeführt wird, um `<xsl:include>` oder `<xsl:import>` aufzulösen.|Geben Sie die Überladung der <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode an, die einen <xref:System.Xml.XmlResolver> als Parameter annimmt. Der <xref:System.Xml.XmlResolver> wird verwendet, um Stylesheets zu laden, auf die durch die `import`-Anweisung oder die `include`-Anweisung verwiesen wird. Wenn Sie `null` übergeben, werden externe Ressourcen nicht aufgelöst.|  
|Während einer Transformation zum Auflösen einer beliebigen `document()`-Funktion.|Geben Sie während der Transformation <xref:System.Xml.XmlResolver> mit der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode an, die ein <xref:System.Xml.XmlResolver>-Argument annimmt.|  
  
 Mit der `document()`-Funktion werden neben den ursprünglichen XML-Daten des Eingabestreams weitere XML-Ressourcen aus einem Stylesheet abgerufen. Da diese Funktion das Einbinden von XML-Daten ermöglicht, die sich an einer anderen Stelle befinden, wird durch einen <xref:System.Xml.XmlResolver> mit einem für die `null`-Methode angegebenen <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Wert das Ausführen der `document()`-Funktion verhindert. Wenn Sie die `document()`-Funktion verwenden möchten, verwenden Sie zusätzlich zum entsprechenden Berechtigungssatz die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode, die einen <xref:System.Xml.XmlResolver> als Parameter annimmt.  
  
 Weitere Informationen zur <xref:System.Xml.Xsl.XslTransform.Load%2A>-Methode und ihrer Verwendung des <xref:System.Xml.XmlResolver> finden Sie unter <xref:System.Xml.Xsl.XslTransform.Load%28System.String%2CSystem.Xml.XmlResolver%29?displayProperty=nameWithType>.  
  
 Wenn die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode aufgerufen wird, werden die Berechtigungen mit den zur Ladezeit bereitgestellten Beweisen berechnet, und dem gesamten Transformationsprozess wird dieser Berechtigungssatz zugewiesen. Bei dem Versuch, durch die `document()`-Funktion eine Aktion zu initiieren, die eine nicht im Berechtigungssatz enthaltene Berechtigung erfordert, wird eine Ausnahme ausgelöst.  
  
## <a name="see-also"></a>Siehe auch

- [XSLT-Transformationen mit der XslTransform-Klasse](xslt-transformations-with-the-xsltransform-class.md)
- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](xsltransform-class-implements-the-xslt-processor.md)
- [Ausgaben aus „XslTransform“](outputs-from-an-xsltransform.md)
- [XSLT-Transformationen über unterschiedliche Speicher](xslt-transformations-over-different-stores.md)
- [„XsltArgumentList“ für Stylesheetparameter und Erweiterungsobjekte](xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md)
- [Skripterstellung für ein XSLT-Stylesheet mit \<msxsl:script>](xslt-stylesheet-scripting-using-msxsl-script.md)
- [Unterstützung der msxsl:node-set()-Funktion](support-for-the-msxsl-node-set-function.md)
- [„XPathNavigator“ in Transformationen](xpathnavigator-in-transformations.md)
- [„XPathNodeIterator“ in Transformationen](xpathnodeiterator-in-transformations.md)
- [XPathDocument-Eingaben in XslTransform](xpathdocument-input-to-xsltransform.md)
- [XmlDataDocument-Eingaben in „XslTransform“](xmldatadocument-input-to-xsltransform.md)
- [XmlDocument-Eingaben in „XslTransform“](xmldocument-input-to-xsltransform.md)
