---
title: Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
- My namespace, extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 950592c0fb197959ce1c3cf6128093846a022709
ms.lasthandoff: 03/13/2017

---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a>Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)
Visual Basic bietet eine einfache Möglichkeit zum Bereitstellen benutzerdefinierter `My` Namespaceerweiterungen mithilfe von Visual Studio-Vorlagen. Wenn Sie eine Projektvorlage für das Erstellen Ihrer `My` Erweiterungen sind ein wesentlicher Bestandteil des neuen Projekttyps, fügen Sie können Ihre benutzerdefinierten `My` Erweiterungscode mit dem Projekt, wenn Sie die Vorlage exportieren. Weitere Informationen zum Exportieren von Projektvorlagen finden Sie unter [Gewusst wie: Erstellen von Projektvorlagen](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398).  
  
 Wenn die benutzerdefinierte `My` -Erweiterung in einer einzelnen Codedatei befindet, können Sie die Datei exportieren, als eine Elementvorlage, die Benutzer auf jede Art von Visual Basic-Projekt hinzufügen können. Anschließend können Sie die Elementvorlage, um zusätzliche Funktionen und Verhalten für die benutzerdefinierte Anpassen `My` -Erweiterung in einem Visual Basic-Projekt. Diese Funktionen sind unter anderem:  
  
-   Ermöglicht Benutzern das Verwalten von benutzerdefinierten `My` -Erweiterung aus der **My-Erweiterungen** im Visual Basic-Projekt-Designer auf der Seite.  
  
-   Automatisches Hinzufügen der benutzerdefinierten `My` Erweiterung, wenn ein Verweis auf eine angegebene Assembly zu einem Projekt hinzugefügt wird.  
  
-   Ausblenden der `My` Erweiterung Item-Vorlage in die **hinzufügen** Dialogfeld, sodass es nicht in der Liste der Projektelemente enthalten ist.  
  
 In diesem Thema erläutert, wie ein benutzerdefiniertes Paket `My` -Erweiterung als ausgeblendete Elementvorlage, die von verwaltet werden, kann die **My-Erweiterungen** im Visual Basic-Projekt-Designer auf der Seite. Die benutzerdefinierte `My` Erweiterung kann auch automatisch hinzugefügt werden, wenn ein Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.  
  
## <a name="create-a-my-namespace-extension"></a>Erstellen einer My Namespaceerweiterung  
 Der erste Schritt beim Erstellen eines Bereitstellungspakets für eine benutzerdefinierte `My` -Erweiterung ist, die Erweiterung als einzelne Codedatei zu erstellen. Weitere Informationen und Anleitungen zum Erstellen eines benutzerdefinierten `My` -Erweiterung finden Sie unter [Erweitern der My-Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Exportieren einer My Namespaceerweiterung als Elementvorlage  
 Nachdem Sie eine Codedatei verfügen, enthält Ihre `My` Namespaceerweiterung können Sie die Codedatei als Visual Studio-Elementvorlage exportieren. Informationen zum Exportieren einer Datei als Visual Studio-Elementvorlage finden Sie unter [Gewusst wie: Erstellen von Elementvorlagen](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5).  
  
> [!NOTE]
>  Wenn Ihre `My` Namespaceerweiterung hat eine Abhängigkeit zu einer bestimmten Assembly, können Sie die Elementvorlage automatisch installiert, Anpassen Ihrer `My` Namespaceerweiterung, wenn ein Verweis auf diese Assembly hinzugefügt wird. Daher sollten Sie der Assemblyverweis, wenn Sie die Codedatei als Visual Studio-Elementvorlage exportieren.  
  
## <a name="customize-the-item-template"></a>Anpassen der Elementvorlage  
 Sie können die Elementvorlage aus verwaltet werden die **My-Erweiterungen** im Visual Basic-Projekt-Designer auf der Seite. Sie können auch festlegen, dass die Elementvorlage automatisch hinzugefügt werden soll, wenn ein Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird. Um diese Anpassungen zu aktivieren, Sie fügen eine neue Datei mit dem Namen der CustomData-Datei und in der Vorlage aus, und dann ein neues Element in der XML in der VSTEMPLATE-Datei hinzufügen.  
  
### <a name="add-the-customdata-file"></a>Die CustomData-Datei hinzufügen  
 Die CustomData-Datei ist eine Textdatei mit einer Erweiterung des Dateinamens. CustomData (der Dateiname kann festgelegt werden auf einen anderen Wert für die Vorlage), die XML enthält. Der XML-Code in der CustomData-Datei weist Visual Basic enthalten die `My` Erweiterung, wenn der Benutzer die **My-Erweiterungen** im Visual Basic-Projekt-Designer auf der Seite. Sie können optional Hinzufügen der `AssemblyFullName>` der CustomData-Datei XML-Attribut. Dies weist Visual Basic automatisch installiert, die benutzerdefinierte `My` Erweiterung, wenn ein Verweis auf eine bestimmte Assembly wird dem Projekt hinzugefügt. Sie können Text-Editor oder XML-Editor zum Erstellen der CustomData-Datei zu verwenden, und fügen Sie es in der Elementvorlage komprimierten Ordner (ZIP-Datei).  
  
 Die folgende XML-Code zeigt z. B. den Inhalt einer CustomData-Datei, die das Vorlagenelement in den Ordner My-Erweiterungen eine Visual Basic-Projekt, wenn Sie einen Verweis auf die Assembly Microsoft.VisualBasic.PowerPacks.Vs.dll hinzufügen zum Projekt hinzugefügt wird.  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 Die CustomData-Datei enthält ein `VBMyExtensionTemplate>` -Element, das über die in der folgenden Tabelle aufgeführten Attribute verfügt.  
  
|Attribut|Beschreibung|  
|---|---|  
|`ID`|Erforderlich. Ein eindeutiger Bezeichner für die Erweiterung. Wenn die Erweiterung mit dieser ID dem Projekt bereits hinzugefügt wurde, wird der Benutzer nicht aufgefordert werden, wieder hinzufügen.|  
|`Version`|Erforderlich. Eine Versionsnummer für die Elementvorlage.|  
|`AssemblyFullName`|Optional. Ein Assemblyname. Wenn das Projekt ein Verweis auf diese Assembly hinzugefügt wird, wird der Benutzer aufgefordert, fügen die `My` Erweiterung aus dieser Elementvorlage.|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Hinzufügen der \<CustomDataSignature > Element zur VSTEMPLATE-Datei  
 Identifizieren Sie die Visual Studio-Elementvorlage als eine `My` Namespaceerweiterung, müssen Sie auch die VSTEMPLATE-Datei für Ihre Elementvorlage ändern. Müssen Sie hinzufügen, eine `<CustomDataSignature>` Element, das `<TemplateData>` Element. Die `<CustomDataSignature>` Element muss den Text enthalten `Microsoft.VisualBasic.MyExtension`, wie im folgenden Beispiel gezeigt.  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 Sie können keine Dateien in einem komprimierten Ordner (ZIP-Datei) nicht direkt ändern. Sie müssen die VSTEMPLATE-Datei aus dem komprimierten Ordner kopieren, ändern, und ersetzen die VSTEMPLATE-Datei in einem komprimierten Ordner durch die aktualisierte Version.  
  
 Das folgende Beispiel zeigt den Inhalt einer VSTEMPLATE-Datei, die die `<CustomDataSignature>` Element hinzugefügt.  
  
```  
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
  <TemplateData>  
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>  
    <Name>MyPrinterInfo</Name>  
    <Description>Custom My Extensions Item Template</Description>  
    <ProjectType>VisualBasic</ProjectType>  
    <SortOrder>10</SortOrder>  
    <Icon>__TemplateIcon.ico</Icon>  
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
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
  
## <a name="install-the-template"></a>Installieren Sie die Vorlage  
 Um die Vorlage zu installieren, können Sie den komprimierten Ordner (ZIP-Datei) in den Visual Basic-Element-Vorlagen-Ordner (z. B. Eigene Dateien\Visual Studio 2008\Templates\Item Basic\Allgemein Basic) kopieren. Alternativ können Sie die Vorlage als Visual Studio-Installer (VSI)-Datei veröffentlichen.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern der meine Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)   
 [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Anpassen der-Objekte sind verfügbar für meine](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Meine Erweiterungen-Seite, Projekt-Designer](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
