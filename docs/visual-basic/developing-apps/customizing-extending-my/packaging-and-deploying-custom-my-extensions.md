---
title: "Packaging and Deploying Custom My Extensions (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My namespace, customizing"
  - "My namespace"
  - "My namespace, extending"
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Packaging and Deploying Custom My Extensions (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Visual Basic bietet mit den Visual Studio\-Vorlagen eine einfache Möglichkeit zum Bereitstellen benutzerdefinierter `My`\-Namespaceerweiterungen.  Wenn Sie eine Projektvorlage erstellen, bei der Ihre `My`\-Erweiterungen ein integraler Bestandteil des neuen Projekttyps sind, können Sie einfach Ihren benutzerdefinierten `My`\-Erweiterungscode zum Projekt hinzufügen, wenn Sie die Vorlage exportieren.  Weitere Informationen zum Exportieren von Projektvorlagen finden Sie unter [Gewusst wie: Erstellen von Projektvorlagen](../Topic/How%20to:%20Create%20Project%20Templates.md).  
  
 Wenn sich die benutzerdefinierte `My`\-Erweiterung in einer einzelnen Codedatei befindet, können Sie die Datei als Elementvorlage exportieren, die allen Visual Basic\-Projekttypen hinzugefügt werden kann.  Anschließend können Sie die Elementvorlage anpassen, um zusätzliche Funktionen und Verhalten für die benutzerdefinierte `My`\-Erweiterung in einem Visual Basic\-Projekt hinzuzufügen.  Dies sind unter anderem die folgenden Funktionen:  
  
-   Zulassen, dass die benutzerdefinierte `My`\-Erweiterung auf der Seite **My\-Erweiterungen** im Visual Basic Project Designer verwaltet werden kann.  
  
-   Automatisches Hinzufügen der benutzerdefinierten `My`\-Erweiterung, wenn dem Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.  
  
-   Ausblenden der Elementvorlage der `My`\-Erweiterung im Dialogfeld **Element hinzufügen**, sodass es nicht in der Liste der Projektelemente enthalten ist.  
  
 In diesem Thema wird das Verpacken einer benutzerdefinierte `My`\-Erweiterung als ausgeblendete Elementvorlage beschrieben, die auf der Seite **My\-Erweiterungen** im Visual Basic Project Designer verwaltet werden kann.  Die benutzerdefinierte `My`\-Erweiterung kann auch automatisch hinzugefügt werden, wenn dem Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.  
  
## Erstellen einer My\-Namespaceerweiterung  
 Der erste Schritt beim Erstellen eines Bereitstellungspakets für eine benutzerdefinierte `My`\-Erweiterung ist, die Erweiterung als einzelne Codedatei zu erstellen.  Ausführliche Informationen und Anweisungen zum Erstellen einer benutzerdefinierten `My`\-Erweiterung finden Sie unter [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).  
  
## Exportieren einer My\-Namespaceerweiterung als Elementvorlage  
 Nach dem Erstellen einer Codedatei, in der Ihre `My`\-Namespaceerweiterung enthalten ist, können Sie die Codedatei als Visual Studio\-Elementvorlage exportieren.  Anweisungen zum Exportieren einer Datei als Visual Studio\-Elementvorlage finden Sie unter [Gewusst wie: Erstellen von Elementvorlagen](../Topic/How%20to:%20Create%20Item%20Templates.md).  
  
> [!NOTE]
>  Wenn die `My`\-Namespaceerweiterung über eine Abhängigkeit zu einer bestimmten Assembly verfügt, können Sie die Elementvorlage so anpassen, dass die `My`\-Namespaceerweiterung automatisch installiert wird, wenn ein Verweis auf diese Assembly hinzugefügt wird.  Aus diesem Grund sollte der Assemblyverweis beim Exportieren der Codedatei als Visual Studio\-Elementvorlage nicht mit eingeschlossen werden.  
  
## Anpassen der Elementvorlage  
 Sie können festlegen, dass die Elementvorlage über die Seite **My\-Erweiterungen** im Visual Basic Project Designer verwaltet werden kann.  Sie können außerdem festlegen, dass die Elementvorlage automatisch hinzugefügt wird, wenn dem Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.  Um diese Anpassungen zu aktivieren, fügen Sie der Vorlage eine neue, als CustomData bezeichnete Datei hinzu, und fügen Sie anschließend dem XML\-Code in ihrer VSTEMPLATE\-Datei ein neues Element hinzu.  
  
### Hinzufügen der CustomData\-Datei  
 Bei der CustomData\-Datei handelt es sich um eine Textdatei, die über die Dateinamenerweiterung CustomData verfügt \(für den Dateinamen kann jeder für die Vorlage sinnvolle Name verwendet werden\) und XML\-Code enthält.  Durch den XML\-Code in der CustomData\-Datei wird festgelegt, dass die `My`\-Erweiterung von Visual Basic für die Seite **My\-Erweiterungen** im Visual Basic Project Designer berücksichtigt wird.  Wahlweise können Sie auch das \<`AssemblyFullName>`\-Attribut dem XML\-Code der CustomData\-Datei hinzufügen.  Dadurch wird festgelegt, dass von Visual Basic automatisch die benutzerdefinierte `My`\-Erweiterung installiert wird, wenn dem Projekt ein Verweis zu einer bestimmten Assembly hinzugefügt wird.  Sie können jeden beliebigen Text\- oder XML\-Editor verwenden, um die CustomData\-Datei zu erstellen, und diese dann dem komprimierten Ordner \(ZIP\-Datei\) der Elementvorlage hinzuzufügen.  
  
 Im folgenden XML\-Code wird beispielsweise der Inhalt einer CustomData\-Datei dargestellt, durch die das Vorlagenelement zum Ordner My\-Erweiterungen eines Visual Basic\-Projekts hinzugefügt wird, wenn dem Projekt ein Verweis auf die Assembly Microsoft.VisualBasic.PowerPacks.Vs.dll hinzugefügt wird.  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 Die CustomData\-Datei enthält ein \<`VBMyExtensionTemplate>`\-Element, das über die in der folgenden Tabelle aufgeführten Attribute verfügt.  
  
|||  
|-|-|  
|Attribut|Beschreibung|  
|`ID`|Erforderlich.  Ein eindeutiger Bezeichner für die Erweiterung.  Wenn die Erweiterung mit dieser ID dem Projekt bereits hinzugefügt wurde, wird der Benutzer aufgefordert, sie erneut hinzuzufügen.|  
|`Version`|Erforderlich.  Eine Versionsnummer für die Elementvorlage.|  
|`AssemblyFullName`|Optional.  Ein Assemblyname.  Wenn dem Projekt ein Verweis auf diese Assembly hinzugefügt wird, wird der Benutzer aufgefordert, die `My`\-Erweiterung aus dieser Elementvorlage hinzuzufügen.|  
  
### Hinzufügen des \< CustomDataSignature \>\-Elements zur VSTEMPLATE\-Datei  
 Um die Visual Studio\-Elementvorlage als `My`\-Namespaceerweiterung zu kennzeichnen, müssen Sie auch die VSTEMPLATE\-Datei für Ihre Elementvorlage ändern.  Sie müssen dem `<TemplateData>`\-Element ein `<CustomDataSignature>`\-Element hinzufügen.  Das `<CustomDataSignature>`\-Element muss den Text `Microsoft.VisualBasic.MyExtension` enthalten, wie im folgenden Beispiel dargestellt.  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 Dateien in einem komprimierten Ordner \(ZIP\-Datei\) können nicht direkt geändert werden.  Sie müssen die VSTEMPLATE\-Datei aus dem komprimierten Ordner kopieren, ändern und dann im komprimierten Ordner durch die aktualisierte Version ersetzen.  
  
 Im folgenden Beispiel ist der Inhalt einer VSTEMPLATE\-Datei dargestellt, der das `<CustomDataSignature>`\-Element hinzugefügt wurde.  
  
```  
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
  <TemplateData>  
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>  
    <Name>MyPrinterInfo</Name>  
    <Description>Custom My Extensions Item Template</Description>  
    <ProjectType>VisualBasic</ProjectType>  
    <SortOrder>10</SortOrder>  
    <Icon>__TemplateIcon.ico</Icon>  
    <CustomDataSignature       >Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
  </TemplateData>  
  <TemplateContent>  
    <References />  
    <ProjectItem SubType="Code"   
                 TargetFileName="$fileinputname$.vb"  
                 ReplaceParameters="true"  
     >MyCustomExtensionModule.vb</ProjectItem>  
  </TemplateContent>  
</VSTemplate>  
```  
  
## Installieren der Vorlage  
 Zum Installieren der Vorlage können Sie den komprimierten Ordner \(ZIP\-Datei\) in den Visual Basic\-Elemetvorlagenordner kopieren \(beispielsweise Eigene Dateien\\Visual Studio 2008\\Templates\\Item Templates\\Visual Basic\)  Sie können die Vorlage auch als VSI\-Datei \(Visual Studio Installer\) veröffentlichen.  Informationen zum Veröffentlichen der Vorlage als VSI\-Datei finden Sie unter [NIB: How to: Publish Project Templates](http://msdn.microsoft.com/de-de/b9087f58-64e9-4767-bf54-e3bf40d63b20).  
  
## Siehe auch  
 [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)   
 [Extending the Visual Basic Application Model](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [My\-Erweiterungen\-Seite im Projekt\-Designer](/visual-studio/ide/reference/my-extensions-page-project-designer-visual-basic)