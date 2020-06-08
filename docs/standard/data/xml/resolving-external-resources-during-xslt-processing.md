---
title: Auflösen von externen Ressourcen während der XSLT-Verarbeitung
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 3a59d31c-0ec5-4de6-a2a9-558531c8116e
ms.openlocfilehash: d38aea1a54c93b00ec14c6aac7ed11ceba288f7b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291499"
---
# <a name="resolving-external-resources-during-xslt-processing"></a>Auflösen von externen Ressourcen während der XSLT-Verarbeitung
Während einer XSLT-Transformation müssen Sie u. U. mehrmals externe Ressourcen auflösen.  
  
## <a name="using-the-xmlresolver-class"></a>Verwenden der XmlResolver-Klasse  
 Die <xref:System.Xml.XmlResolver>-Klasse wird zum Auflösen externer Ressourcen verwendet. In der folgenden Tabelle wird dargestellt, wann der <xref:System.Xml.XmlResolver> während der XSLT-Verarbeitung aktiv wird.  
  
|XSLT-Aufgabe|Verwendung von "XmlResolver"|  
|---------------|--------------------------------------|  
|Kompilieren des Stylesheets.|Auflösen des URI des Stylesheets.<br /><br /> - und -<br /><br /> Auflösen von URI-Verweisen in allen `xsl:import`-Elementen oder `xsl:include`-Elementen.|  
|Ausführen des Stylesheets.|Auflösen des URI des Kontextmenüs.<br /><br /> - und -<br /><br /> Auflösen von URI-Verweisen in beliebigen Funktionen von XSLT-`document()`.|  
  
 Die <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode und die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode enthalten Überladungen, die ein <xref:System.Xml.XmlResolver>-Objekt als eines ihrer Argumente verwenden. Wenn kein <xref:System.Xml.XmlResolver> angegeben ist, wird ein Standard-<xref:System.Xml.XmlUrlResolver> ohne Anmeldeinformationen verwendet.  
  
 In der folgenden Liste wird erläutert, wann ein <xref:System.Xml.XmlResolver>-Objekt angegeben werden kann.  
  
- Wenn der XSLT-Vorgang auf eine Netzwerkressource zugreifen muss, die eine Authentifizierung erfordert, können Sie einen <xref:System.Xml.XmlResolver> mit den notwendigen Anmeldeinformationen verwenden.  
  
- Wenn Sie die Ressourcen einschränken möchten, auf die der XSLT-Vorgang zugreifen kann, können Sie einen <xref:System.Xml.XmlSecureResolver> mit den korrekt festgelegten Einstellungen verwenden. Verwenden Sie die <xref:System.Xml.XmlSecureResolver>-Klasse, wenn Sie eine Ressource öffnen möchten, die nicht von Ihnen gesteuert wird oder die nicht vertrauenswürdig ist.  
  
- Wenn Sie das Verhalten anpassen möchten, können Sie eine eigene <xref:System.Xml.XmlResolver>-Klasse implementieren und diese zum Auflösen von Ressourcen verwenden.  
  
- Wenn Sie sich vergewissern möchten, dass auf keine externe Ressource zugegriffen wird, können Sie für das `null`-Argument <xref:System.Xml.XmlResolver> angeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Stylesheet kompiliert, das in einer Netzwerkressource gespeichert ist. Ein <xref:System.Xml.XmlUrlResolver>-Objekt gibt die Anmeldeinformationen an, die für den Zugriff auf das Stylesheet erforderlich sind.  
  
 [!code-csharp[XslCompiledTransform.Load#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Load/CS/Xslt_Load_v2.cs#11)]
 [!code-vb[XslCompiledTransform.Load#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Load/VB/Xslt_Load_v2.vb#11)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Xsl.XslCompiledTransform>
- <xref:System.Xml.Xsl.XsltSettings>
- [XSLT Transformations (XSLT-Transformationen)](xslt-transformations.md)
