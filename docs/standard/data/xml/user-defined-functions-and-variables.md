---
title: Benutzerdefinierte Funktionen und Variablen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4772f20e-1e7f-496e-93c2-1484473be555
ms.openlocfilehash: c1f519dd539a266d61945ad221bccceaa1361779
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675619"
---
# <a name="user-defined-functions-and-variables"></a>Benutzerdefinierte Funktionen und Variablen

Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt eine Gruppe von Methoden bereit, die zur Interaktion mit <xref:System.Xml.XPath.XPathDocument>-Daten verwendet werden. Sie können die standardmäßigen XPath-Funktionen durch Implementieren von Erweiterungsfunktionen und -variablen für XPath-Abfrageausdrücke ersetzen. Die <xref:System.Xml.XPath.XPathExpression.SetContext%2A>-Methode akzeptiert einen von <xref:System.Xml.Xsl.XsltContext> abgeleiteten benutzerdefinierten Kontext. Benutzerdefinierte Funktionen werden von dem benutzerdefinierten Kontext aufgelöst.  
  
 Erweiterungsfunktionen und -variablen können nützlich zum Vermeiden von XML-Injection-Angriffen sein. In diesen Szenarios werden Benutzereingaben benutzerdefinierten Variablen zugewiesen und mittels Erweiterungsfunktionen verarbeitet und nicht einfach mit Verarbeitungsanweisungen verkettet. Erweiterungsfunktionen und -variablen enthalten Benutzereingaben, sodass nur die vom Designer vorgesehenen Aktionen für XML-Daten ausgeführt werden.  
  
 Zum Verwenden von Erweiterungen implementieren Sie eine benutzerdefinierte <xref:System.Xml.Xsl.XsltContext>-Klasse mit den Schnittstellen <xref:System.Xml.Xsl.IXsltContextFunction> und <xref:System.Xml.Xsl.IXsltContextVariable>, die Erweiterungsfunktionen und -variablen unterstützen. Ein <xref:System.Xml.XPath.XPathExpression> fügt Benutzereingaben mithilfe des zugehörigen <xref:System.Xml.Xsl.XsltArgumentList>-Elements dem benutzerdefinierten <xref:System.Xml.Xsl.XsltContext> hinzu.  
  
 Der <xref:System.Xml.XPath.XPathExpression> stellt eine kompilierte Abfrage dar, die vom <xref:System.Xml.XPath.XPathNavigator> verwendet wird, um die im Ausdruck bezeichneten Knoten zu suchen und zu verarbeiten.  
  
 Das folgende Beispiel zeigt die Implementierung einer benutzerdefinierten Kontextklasse, die von <xref:System.Xml.Xsl.XsltContext> abgeleitet ist. In den Kommentaren im Code werden Klassenmember und deren Verwendung in benutzerdefinierten Funktionen beschrieben. Auf dieses Codesegment folgen Implementierungen von Funktionen und Variablen und eine Beispielanwendung, die diese Implementierungen verwendet.  
  
 [!code-csharp[XPathExtensionFunctions#2](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#2)]
 [!code-vb[XPathExtensionFunctions#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#2)]  
  
 Mit dem folgenden Code wird das <xref:System.Xml.Xsl.IXsltContextFunction>-Element implementiert. Die Klasse, die das <xref:System.Xml.Xsl.IXsltContextFunction>-Element implementiert, löst benutzerdefinierte Funktionen auf und führt sie aus. In diesem Beispiel wird die mit der folgenden Deklaration identifizierte Funktion verwendet: `private int CountChar(string title, char charTocount)`.  
  
 Mit den Kommentaren im Code werden Klassenmember beschrieben.  
  
 [!code-csharp[XPathExtensionFunctions#3](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#3)]
 [!code-vb[XPathExtensionFunctions#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#3)]  
  
 Mit dem folgenden Code wird das <xref:System.Xml.Xsl.IXsltContextVariable>-Element implementiert. Diese Klasse löst Verweise auf benutzerdefinierte Variablen in XPath-Abfrageausdrücken zur Laufzeit auf. Eine Instanz dieser Klasse wird erstellt und von der überschriebenen <xref:System.Xml.Xsl.XsltContext.ResolveVariable%2A>-Methode der benutzerdefinierten <xref:System.Xml.Xsl.XsltContext>-Klasse zurückgegeben.  
  
 Mit den Kommentaren im Code werden die Klassenmember beschrieben.  
  
 [!code-csharp[XPathExtensionFunctions#4](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#4)]
 [!code-vb[XPathExtensionFunctions#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#4)]  
  
 Im folgenden Code wird die benutzerdefinierte Funktion verwendet, um die Zeichen in den Elementen des `Tasks.xml`-Dokuments zu zählen (mit den vorherigen gültigen Klassendefinitionen). Mit den Kommentaren im Code wird der Code beschrieben, der die benutzerdefinierte Funktion kompiliert und auf das `Tasks.xml`-Dokument anwendet.  
  
 [!code-csharp[XPathExtensionFunctions#1](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#1)]
 [!code-vb[XPathExtensionFunctions#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#1)]  
  
 In diesem Beispiel werden die folgenden XML-Daten verwendet.  
  
 [!code-xml[XPathExtensionFunctions#5](../../../../samples/snippets/xml/VS_Snippets_Data/xpathextensionfunctions/XML/tasks.xml#5)]
