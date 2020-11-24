---
title: XSLT-Sicherheitsaspekte
ms.date: 03/30/2017
ms.assetid: fea695be-617c-4977-9567-140e820436fc
ms.openlocfilehash: ad96ebb6048e8a397e0761a2217fec89e0d206b0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818283"
---
# <a name="xslt-security-considerations"></a>XSLT-Sicherheitsaspekte
Die Sprache XSLT verfügt über eine Vielzahl an Funktionen für eine hohe Leistungsfähigkeit und Flexibilität. Sie enthält viele Funktionen, die zwar hilfreich sind, jedoch auch von externen Quellen ausgenutzt werden können. Um die XSLT-Sicherheit zu verwenden, müssen Sie die verschiedenen Arten von Sicherheitsproblemen kennen und die grundlegenden Strategien verstehen, mit denen Sie diese verringern können.  
  
## <a name="xslt-extensions"></a>XSLT-Erweiterungen  
 Zwei häufig verwendete XSLT-Erweiterungen sind Stylesheet-Skriptobjekte und Erweiterungsobjekte. Diese Erweiterungen ermöglichen dem XSLT-Prozessor das Ausführen von Code.  
  
- Mit Erweiterungsobjekten werden XSL-Transformationen Programmierfunktionen hinzugefügt.  
  
- Skripts können mithilfe des `msxsl:script`-Erweiterungselements in das Stylesheet eingebettet werden.  
  
### <a name="extension-objects"></a>Erweiterungsobjekte  
 Erweiterungsobjekte werden mithilfe der <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>-Methode hinzugefügt. Für die Unterstützung von Erweiterungsobjekten muss der FullTrust-Berechtigungssatz festgelegt sein. Dadurch wird sichergestellt, dass beim Ausführen von Erweiterungsobjektcode keine Erhöhung der Berechtigungen auftritt. Ohne FullTrust-Berechtigung wird durch den Versuch, die <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>-Methode aufzurufen, eine Sicherheitsausnahme ausgelöst.  
  
### <a name="style-sheet-scripts"></a>Stylesheetskripts  
 Skripts können mithilfe des `msxsl:script`-Erweiterungselements in ein Stylesheet eingebettet werden. Die Skriptunterstützung ist eine optionale Funktion der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse, die in der Standardeinstellung deaktiviert ist. Die Skriptunterstützung kann aktiviert werden, indem die <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A?displayProperty=nameWithType>-Eigenschaft auf `true` festgelegt wird und das <xref:System.Xml.Xsl.XsltSettings>-Objekt an die <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode übergeben wird.  
  
#### <a name="guidelines"></a>Richtlinien  
 Aktivieren Sie die Skriptunterstützung nur, wenn das Stylesheet aus einer vertrauenswürdigen Quelle stammt. Wenn Sie die Quelle des Stylesheets nicht überprüfen können oder das Stylesheet nicht aus einer vertrauenswürdigen Quelle stammt, übergeben Sie `null` für das Argument der XSLT-Einstellungen.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Die Sprache XSLT verfügt über Funktionen wie `xsl:import`, `xsl:include` oder die `document()`-Funktion, in denen der Prozessor URI-Verweise auflösen muss. Die <xref:System.Xml.XmlResolver>-Klasse wird zum Auflösen externer Ressourcen verwendet. Externe Ressourcen müssen u. U. in den folgenden zwei Fällen aufgelöst werden:  
  
- Beim Kompilieren eines Stylesheets wird der <xref:System.Xml.XmlResolver> für die Auflösung von `xsl:import` und `xsl:include` verwendet.  
  
- Beim Ausführen der Transformation wird die <xref:System.Xml.XmlResolver>-Funktion mithilfe des `document()` aufgelöst.  
  
    > [!NOTE]
    > Die `document()`-Funktion ist für die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse in der Standardeinstellung deaktiviert. Diese Funktion kann aktiviert werden, indem die <xref:System.Xml.Xsl.XsltSettings.EnableDocumentFunction%2A?displayProperty=nameWithType>-Eigenschaft auf `true` festgelegt wird und das <xref:System.Xml.Xsl.XsltSettings>-Objekt an die <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode übergeben wird.  
  
 Die <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode und die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode enthalten Überladungen, die einen <xref:System.Xml.XmlResolver> als eines ihrer Argumente akzeptieren. Wenn kein <xref:System.Xml.XmlResolver> angegeben ist, wird ein Standard-<xref:System.Xml.XmlUrlResolver> ohne Anmeldeinformationen verwendet.  
  
#### <a name="guidelines"></a>Richtlinien  
 Aktivieren Sie die `document()`-Funktion nur, wenn das Stylesheet aus einer vertrauenswürdigen Quelle stammt.  
  
 In der folgenden Liste wird erläutert, wann ein <xref:System.Xml.XmlResolver>-Objekt angegeben werden kann.  
  
- Wenn der XSLT-Vorgang auf eine Netzwerkressource zugreifen muss, die eine Authentifizierung erfordert, können Sie einen <xref:System.Xml.XmlResolver> mit den notwendigen Anmeldeinformationen verwenden.  
  
- Wenn Sie die Ressourcen einschränken möchten, auf die der XSLT-Vorgang zugreifen kann, können Sie einen <xref:System.Xml.XmlSecureResolver> mit den korrekt festgelegten Einstellungen verwenden. Verwenden Sie die <xref:System.Xml.XmlSecureResolver>-Klasse, wenn Sie eine Ressource öffnen möchten, die nicht von Ihnen gesteuert wird oder die nicht vertrauenswürdig ist.  
  
- Wenn Sie das Verhalten anpassen möchten, können Sie eine eigene <xref:System.Xml.XmlResolver>-Klasse implementieren und diese zum Auflösen von Ressourcen verwenden.  
  
- Wenn Sie sich vergewissern möchten, dass auf keine externe Ressource zugegriffen wird, können Sie für das `null`-Argument <xref:System.Xml.XmlResolver> angeben.  
  
## <a name="see-also"></a>Siehe auch

- [XSLT Transformations (XSLT-Transformationen)](xslt-transformations.md)
- [Auflösen von externen Ressourcen während der XSLT-Verarbeitung](resolving-external-resources-during-xslt-processing.md)
- [Codezugriffssicherheit](../../../framework/misc/code-access-security.md)
