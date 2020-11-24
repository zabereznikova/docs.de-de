---
title: Skriptblöcke, die "msxsl:script" verwenden
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fde6f43f-c594-486f-abcb-2211197fae20
ms.openlocfilehash: 3cb65142243d1f910ffd0fb85750ba62786d79f0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824696"
---
# <a name="script-blocks-using-msxslscript"></a>Skriptblöcke, die "msxsl:script" verwenden
Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse unterstützt eingebettete Skripts unter Verwendung des `msxsl:script`-Elements. Beim Laden des Stylesheets werden alle definierten Funktionen von CodeDOM (Code Document Object Model) in die Microsoft Intermediate Language (MSIL) kompiliert und zur Laufzeit ausgeführt. Die aus dem eingebetteten Skriptblock generierte Assembly und die für das Stylesheet generierte Assembly sind voneinander verschieden.  
  
## <a name="enable-xslt-script"></a>Aktivieren von XSLT-Skript  
 Die Unterstützung für eingebettete Skripts ist eine optionale XSLT-Einstellung für die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse. Die Skriptunterstützung ist in der Standardeinstellung deaktiviert. Sie können die Skriptunterstützung aktivieren, indem Sie ein <xref:System.Xml.Xsl.XsltSettings>-Objekt erstellen, bei dem die <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A>-Eigenschaft auf `true` festgelegt wurde, und das Objekt an die <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode übergeben.  
  
> [!NOTE]
> XSLT-Skripts sollten nur aktiviert werden, wenn eine Skriptunterstützung erforderlich ist und Sie mit einer vollständig vertrauenswürdigen Umgebung arbeiten.  
  
## <a name="msxslscript-element-definition"></a>Elementdefinition von "msxsl:script"  
 Das `msxsl:script`-Element ist eine Microsoft-Erweiterung der XSLT 1.0-Empfehlung und weist folgende Definition auf:  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 Das `msxsl`-Präfix ist an den `urn:schemas-microsoft-com:xslt`-Namespace-URI gebunden. Das Stylesheet muss die `xmlns:msxsl=urn:schemas-microsoft-com:xslt`-Namespacedeklaration enthalten.  
  
 Das `language`-Attribut ist optional. Sein Wert entspricht der Codesprache des eingebetteten Codeblocks. Die Sprache wird mithilfe der <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType>-Methode dem entsprechenden CodeDOM-Compiler zugeordnet. Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse unterstützt alle Microsoft .NET-Sprachen, vorausgesetzt, der entsprechende Anbieter ist auf dem Computer installiert und im Abschnitt "system.codedom" der Datei "machine.config" registriert. Wenn kein `language`-Attribut angegeben ist, wird die Standardsprache JScript verwendet. Beim Namen der Sprache wird die Groß- und Kleinschreibung nicht berücksichtigt, daher sind "JavaScript" und "javascript" identisch.  
  
 Das `implements-prefix`-Attribut ist erforderlich. Mit diesem Attribut wird ein Namespace deklariert und mit dem Skriptblock verknüpft. Der Wert dieses Attributs ist das Präfix, das den Namespace darstellt. Dieses Präfix kann an einer beliebigen Stelle im Stylesheet definiert werden.  
  
> [!NOTE]
> Bei Verwendung des `msxsl:script`-Elements wird dringend empfohlen, das Skript ungeachtet der verwendeten Sprache in einem CDATA-Abschnitt zu platzieren. Da das Skript Operatoren, Bezeichner oder Trennzeichen für eine bestimmte Sprache enthalten kann, wenn es nicht in einem CDATA-Abschnitt enthalten ist, kann es möglicherweise als XML fehlinterpretiert werden. Der folgende XML-Code zeigt eine Vorlage des CDATA-Abschnitts, in dem Code platziert werden kann.  
  
```xml  
<msxsl:script implements-prefix='your-prefix' language='CSharp'>  
<![CDATA[  
// Code block.  
]]>  
</msxsl:script>  
```  
  
## <a name="script-functions"></a>Skriptfunktionen  
 Funktionen können innerhalb des `msxsl:script`-Elements deklariert werden. Wenn eine Funktion deklariert wurde, ist sie in einem Skriptblock enthalten. Stylesheets können mehrere voneinander unabhängige Skriptblöcke enthalten. Sie können daher bei der Ausführung innerhalb eines Skriptblocks nur dann eine Funktion aufrufen, die Sie in einem anderen Skriptblock definiert haben, wenn diese Funktion so deklariert wurde, dass sie den gleichen Namespace und die gleiche Skriptsprache verwendet. Da jeder Skriptblock in einer eigenen Sprache vorliegen kann und der Block gemäß der Grammatikregeln für den betreffenden Sprachparser analysiert wird, wird empfohlen, die korrekte Syntax für die verwendete Sprache einzuhalten. Verwenden Sie z. B. in einem Microsoft C#-Skriptblock die Kommentarsyntax von C#.  
  
 Die bereitgestellten Argumente und Rückgabewerte für die Funktion können einen beliebigen Typ aufweisen. Da die XPath-Typen des W3C eine Teilmenge der CLR-Typen (Common Language Runtime) sind, findet die Typkonvertierung für Typen statt, die nicht als XPath-Typen betrachtet werden. In der folgenden Tabelle werden die entsprechenden W3C-Typen und die äquivalenten CLR-Typen aufgelistet.  
  
|W3C-Typ|CLR-Typ|  
|--------------|--------------|  
|`String`|<xref:System.String>|  
|`Boolean`|<xref:System.Boolean>|  
|`Number`|<xref:System.Double>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator>|  
  
 Numerische CLR-Typen werden in <xref:System.Double> konvertiert. Der <xref:System.DateTime>-Typ wird in <xref:System.String> konvertiert. <xref:System.Xml.XPath.IXPathNavigable>-Typen werden in <xref:System.Xml.XPath.XPathNavigator> konvertiert. **XPathNavigator[]** wird in <xref:System.Xml.XPath.XPathNodeIterator> konvertiert.  
  
 Alle anderen Typen lösen einen Fehler aus.  
  
### <a name="importing-namespaces-and-assemblies"></a>Importieren von Namespaces und Assemblys  
 Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse definiert eine Gruppe von Assemblys und Namespaces vor, die in der Standardeinstellung vom `msxsl:script`-Element unterstützt werden. Sie können jedoch Klassen und Member verwenden, die zu einem Namespace gehören, der nicht in der vordefinierten Liste aufgeführt ist, indem Sie die Assembly und den Namespace in den `msxsl:script`-Block importieren.  
  
#### <a name="assemblies"></a>Assemblys  
 In der Standardeinstellung wird auf die folgenden zwei Assemblys verwiesen:  
  
- System.dll  
  
- System.Xml.dll  
  
- Microsoft.VisualBasic.dll (bei Skriptsprache VB)  
  
 Mithilfe des `msxsl:assembly`-Elements können Sie die zusätzlichen Assemblys importieren. Dies gilt auch für die Assembly beim Kompilieren des Stylesheets. Das `msxsl:assembly`-Element weist folgende Definition auf:  
  
```xml  
<msxsl:script>  
  <msxsl:assembly name="system.assemblyName" />  
  <msxsl:assembly href="path-name" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
 Das `name`-Attribut enthält den Namen der Assembly, und das `href`-Attribut enthält den Pfad der Assembly. Der Assemblyname kann ein vollständiger Name sein, z. B. "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089", oder ein Kurzname wie "System.Web".  
  
#### <a name="namespaces"></a>Namespaces  
 In der Standardeinstellung sind die folgenden Namespaces enthalten:  
  
- System  
  
- System.Collection  
  
- System.Text  
  
- System.Text.RegularExpressions  
  
- System.Xml  
  
- System.Xml.Xsl  
  
- System.Xml.XPath  
  
- Microsoft.VisualBasic (bei Skriptsprache VB)  
  
 Mithilfe des `namespace`-Attributs können Sie Unterstützung für zusätzliche Namespaces hinzufügen. Der Attributwert ist der Name des Namespaces.  
  
```xml  
<msxsl:script>  
  <msxsl:using namespace="system.namespaceName" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Umfang eines Kreises bei angegebenem Radius unter Verwendung eines eingebetteten Skripts berechnet.  
  
 [!code-csharp[XSLT_Script#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Script/CS/xslt_script.cs#1)]
 [!code-vb[XSLT_Script#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Script/VB/xslt_script.vb#1)]  
  
#### <a name="numberxml"></a>number.xml  
 [!code-xml[XSLT_Script#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/number.xml#2)]  
  
#### <a name="calcxsl"></a>calc.xsl  
 [!code-xml[XSLT_Script#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/calc.xsl#3)]  
  
### <a name="output"></a>Output  
  
```xml  
<circles xmlns:msxsl="urn:schemas-microsoft-com:xslt" xmlns:user="urn:my-scripts">  
  <circle>  
    <radius>12</radius>  
    <circumference>75.36</circumference>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
    <circumference>235.5</circumference>  
  </circle>  
</circles>  
```  
  
## <a name="see-also"></a>Siehe auch

- [XSLT Transformations (XSLT-Transformationen)](xslt-transformations.md)
- [Generieren und Kompilieren von dynamischem Quellcode](../../../framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)
