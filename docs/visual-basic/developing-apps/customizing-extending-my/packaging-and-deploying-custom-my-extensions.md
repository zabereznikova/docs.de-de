---
title: Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 901d0b80a18d2f4d262cc65eb485dcc628bc6a08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591858"
---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a>Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)
Visual Basic bietet eine einfache Möglichkeit zum Bereitstellen benutzerdefinierter `My` Namespaceerweiterungen mithilfe von Visual Studio-Vorlagen. Wenn Sie eine Projektvorlage für das Erstellen Ihrer `My` Erweiterungen sind ein wesentlicher Bestandteil der neuen Projekttyp, Sie können nur einschließen, die benutzerdefinierte `My` Erweiterungscode mit dem Projekt aus, wenn Sie die Vorlage exportieren. Weitere Informationen zum Exportieren von Projektvorlagen finden Sie unter [Vorgehensweise: Erstellen von Projektvorlagen](/visualstudio/ide/how-to-create-project-templates).  
  
 Wenn Ihre benutzerdefinierte `My` Erweiterung in einer einzelnen Codedatei ist, können Sie die Datei exportieren, wie eine Elementvorlage, die Benutzer auf einen beliebigen Typ von Visual Basic-Projekt hinzufügen können. Anschließend können Sie die Elementvorlage, um zusätzliche Funktionen und Verhalten für die benutzerdefinierte Anpassen `My` Erweiterung in einem Visual Basic-Projekt. Diese Funktionen umfassen Folgendes:  
  
-   Ermöglicht Benutzern das Verwalten Ihrer benutzerdefinierten `My` Erweiterung aus der **My-Erweiterungen** auf der Seite der Visual Basic-Projekt-Designer.  
  
-   Automatisches Hinzufügen von benutzerdefinierten `My` Erweiterung auf, wenn ein Verweis auf eine angegebene Assembly zu einem Projekt hinzugefügt wird.  
  
-   Ausblenden der `My` Erweiterung Elementvorlage in der **Element hinzufügen** Dialogfeld, damit er nicht in der Liste der Projektelemente eingeschlossen ist.  
  
 In diesem Thema wird erläutert, wie eine benutzerdefinierte verpackt `My` Erweiterung als ausgeblendete Elementvorlage, die von verwaltet werden kann die **My-Erweiterungen** auf der Seite der Visual Basic-Projekt-Designer. Die benutzerdefinierte `My` Erweiterung kann auch automatisch hinzugefügt werden, wenn ein Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.  
  
## <a name="create-a-my-namespace-extension"></a>Erstellen Sie einen Namespace-Erweiterung  
 Der erste Schritt beim Erstellen eines Bereitstellungspakets für eine benutzerdefinierte `My` -Erweiterung besteht darin, die Erweiterung als einzelne Codedatei zu erstellen. Weitere Informationen und Anleitungen zum Erstellen eines benutzerdefinierten `My` Erweiterung finden Sie unter [erweitern den My-Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Exportieren einer meiner Namespaceerweiterung als eine Elementvorlage  
 Nach dem Sie eine Codedatei, enthalten Ihre `My` Namespaceerweiterung, Sie können die Codedatei als Visual Studio-Elementvorlage exportieren. Anweisungen zum Exportieren einer Datei als Visual Studio-Elementvorlage, finden Sie unter [Vorgehensweise: Erstellen von Elementvorlagen](/visualstudio/ide/how-to-create-item-templates).  
  
> [!NOTE]
>  Wenn Ihre `My` Namespaceerweiterung hat eine Abhängigkeit zu einer bestimmten Assembly, können Sie die Elementvorlage zur automatischen Installation anpassen Ihrer `My` Namespaceerweiterung auf, wenn ein Verweis auf diese Assembly hinzugefügt wird. Daher sollten Sie der Assemblyverweis, wenn Sie die Codedatei als Visual Studio-Elementvorlage exportieren.  
  
## <a name="customize-the-item-template"></a>Anpassen der Elementvorlage  
 Sie können die Elementvorlage aus verwaltet werden die **My-Erweiterungen** auf der Seite der Visual Basic-Projekt-Designer. Sie können auch die Elementvorlage automatisch hinzugefügt werden soll, wenn ein Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird. Um diese Anpassungen ausführen können, Sie fügen eine neue Datei namens der CustomData-Datei, in der Vorlage aus, und klicken Sie dann ein neues Element in der XML in der VSTEMPLATE-Datei hinzufügen.  
  
### <a name="add-the-customdata-file"></a>Die CustomData-Datei hinzufügen  
 Die CustomData-Datei ist eine Textdatei mit der Dateinamenerweiterung. Die CustomData-Funktion (der Dateiname kann festgelegt werden auf einen beliebigen Wert sinnvoll, eine Vorlage) und XML enthält. Der XML-Code in der CustomData-Datei weist Visual Basic umfassen die `My` Erweiterung auf, wenn der Benutzer verwenden die **My-Erweiterungen** Visual Basic-Projekt-Designer auf der Seite. Sie können optional hinzufügen, die <`AssemblyFullName>` der CustomData-Datei XML-Attribut. Dies weist Visual Basic zur automatischen Installation von benutzerdefinierten `My` Erweiterung auf, wenn ein Verweis auf eine bestimmte Assembly wird dem Projekt hinzugefügt. Sie können jeden beliebigen Text- oder XML-Editor zum Erstellen der CustomData-Datei verwenden und fügen Sie ihn anschließend in der Elementvorlage komprimierten Ordner (ZIP-Datei).  
  
 Das folgende XML zeigt z. B. den Inhalt einer CustomData-Datei, die das Vorlagenelement in den Ordner "My-Erweiterungen" von einer Visual Basic-Projekt, wenn ein Verweis auf die Assembly Microsoft.VisualBasic.PowerPacks.Vs.dll hinzugefügt wird dem Projekt hinzugefügt wird.  
  
```xml  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 Die CustomData-Datei enthält ein <`VBMyExtensionTemplate>` Element mit Attributen wie in der folgenden Tabelle aufgeführt.  
  
|Attribut|Beschreibung|  
|---|---|  
|`ID`|Erforderlich. Ein eindeutiger Bezeichner für die Erweiterung. Wenn die Erweiterung, die diese ID weist das Projekt bereits hinzugefügt wurde, wird der Benutzer nicht aufgefordert werden, Sie es dann erneut hinzuzufügen.|  
|`Version`|Erforderlich. Eine Versionsnummer für die Elementvorlage.|  
|`AssemblyFullName`|Dies ist optional. Ein Assemblyname. Wenn Sie dem Projekt ein Verweis auf diese Assembly hinzugefügt wird, wird der Benutzer aufgefordert, Hinzufügen der `My` Erweiterung von diesem Elementvorlage.|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Hinzufügen der \<CustomDataSignature >-Element in der VSTEMPLATE-Datei  
 Identifizieren Sie die Visual Studio-Elementvorlage als eine `My` Namespaceerweiterung, müssen Sie auch die VSTEMPLATE-Datei für die Elementvorlage ändern. Müssen Sie hinzufügen, eine `<CustomDataSignature>` Element an der `<TemplateData>` Element. Die `<CustomDataSignature>` -Element muss den Text enthalten `Microsoft.VisualBasic.MyExtension`, wie im folgenden Beispiel gezeigt.  
  
```xml  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 Dateien in einem komprimierten Ordner (ZIP-Datei) kann nicht direkt geändert werden. Sie müssen kopieren Sie die VSTEMPLATE-Datei aus dem komprimierten Ordner ändern, und Ersetzen Sie die VSTEMPLATE-Datei in den komprimierten Ordner durch die aktualisierte Kopie.  
  
 Das folgende Beispiel zeigt den Inhalt einer VSTEMPLATE-Datei mit den `<CustomDataSignature>` Element hinzugefügt.  
  
```xml  
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
 Um die Vorlage zu installieren, können Sie den komprimierten Ordner (ZIP-Datei) in den Visual Basic-Element-Vorlagen-Ordner (z. B. Eigene Dateien\Visual Studio 2008\Templates\Item Templates\Visual Basic) kopieren. Alternativ können Sie die Vorlage als Visual Studio-Installer (VSI)-Datei veröffentlichen.  
  
## <a name="see-also"></a>Siehe auch  
 [Extending the My Namespace in Visual Basic (Erweitern des Namespaces „My“ in Visual Basic)](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)  
 [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [My-Erweiterungen-Seite, Projekt-Designer](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
