---
title: Packen und Bereitstellen von benutzerdefinierten My-Erweiterungen
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 6d2cc2b01b04b30bd3b1a4371352ded20ea8664b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411752"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>Packen und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)

Visual Basic stellt eine einfache Möglichkeit für Sie zur Verfügung, Ihre benutzerdefinierten `My`-Namespaceerweiterungen bereitzustellen, indem Visual Studio-Vorlagen verwendet werden. Wenn Sie eine Projektvorlage erstellen, für die Ihre `My`-Erweiterungen ein integraler Bestandteil des neuen Projekttyps sind, können Sie einfach Ihren benutzerdefinierten `My`-Erweiterungscode mit dem Projekt einschließen, wenn Sie die Vorlage exportieren. Weitere Informationen zum Exportieren von Projektvorlagen finden Sie unter [Vorgehensweise: Erstellen von Projektvorlagen](/visualstudio/ide/how-to-create-project-templates).

Wenn sich Ihre benutzerdefinierte `My`-Erweiterung in einer einzelnen Codedatei befindet, können Sie die Datei als eine Elementvorlage exportieren, die Benutzer jedem beliebigen Visual Basic-Projekttyp hinzufügen können. Sie können die Elementvorlage dann anpassen, um in einem Visual Basic-Projekt zusätzliche Funktionen und weiteres Verhalten für Ihre benutzerdefinierte `My`-Erweiterung zu aktivieren. Zu diesen Funktionen gehören die folgenden:

- Zulassen, dass Benutzer Ihre benutzerdefinierte `My`-Erweiterung auf der Seite **Meine Erweiterungen** des Projekt-Designers in Visual Basic verwalten

- Automatisches Hinzufügen Ihrer benutzerdefinierten `My`-Erweiterung, wenn ein Verweis auf eine angegebene Assembly einem Projekt hinzugefügt wird.

- Ausblenden der `My`-Erweiterungselementvorlage im **Element hinzufügen**-Dialogfeld, sodass sie nicht in der Liste der Projektelemente angezeigt wird

In diesem Thema wird erläutert, wie eine benutzerdefinierte `My`-Erweiterung als ausgeblendete Elementvorlage gepackt werden kann, die über die Seite **Meine Erweiterungen** des Projekt-Designers in Visual Basic verwaltet werden kann. Die benutzerdefinierte `My`-Erweiterung kann auch automatisch hinzugefügt werden, wenn ein Verweis auf eine angegebene Assembly einem Projekt hinzugefügt wird.

## <a name="create-a-my-namespace-extension"></a>Erstellen einer My-Namespaceerweiterung

Der erste Schritt für die Erstellung eines Bereitstellungspakets für eine benutzerdefinierte `My`-Erweiterung ist das Erstellen der Erweiterung als einzelne Codedatei. Details und eine Anleitung, wie Sie eine benutzerdefinierte `My`-Erweiterung erstellen, finden Sie unter [Erweitern des My-Namespace in Visual Basic](extending-the-my-namespace.md).

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Exportieren einer My-Namespaceerweiterung als Elementvorlage

Nachdem Sie eine Codedatei erstellt haben, die Ihre `My`-Namespaceerweiterung beinhaltet, können Sie die Codedatei als Visual Studio-Elementvorlage exportieren. Eine Anleitung zum Exportieren einer Datei als Visual Studio-Elementvorlage finden Sie unter [Vorgehensweise: Erstellen von Elementvorlagen](/visualstudio/ide/how-to-create-item-templates).

> [!NOTE]
> Wenn Ihre `My`-Namespaceerweiterung eine Abhängigkeit von einer bestimmten Assembly aufweist, können Sie die Elementvorlage so anpassen, dass Ihre `My`-Namespaceerweiterung automatisch installiert wird, wenn ein Verweis auf diese Assembly hinzugefügt wird. Dies hat zur Folge, dass Sie diesen Assemblyverweis ausschließen sollten, wenn Sie die Codedatei als Visual Studio-Elementvorlage exportieren.

## <a name="customize-the-item-template"></a>Anpassen der Elementvorlage

Sie können aktivieren, dass Ihre Elementvorlage über die Seite **Meine Erweiterungen** des Projekt-Designers in Visual Basic verwaltet werden kann. Sie können auch aktivieren, dass die Elementvorlage automatisch hinzugefügt wird, wenn ein Verweis auf eine angegebene Assembly einem Projekt hinzugefügt wird. Wenn Sie diese Anpassungen aktivieren möchten, fügen Sie Ihrer Vorlage eine neue Datei hinzu, die als CustomData-Datei bezeichnet wird. Dann fügen Sie im XML-Code in Ihrer VSTEMPLATE-Datei ein neues Element hinzu.

### <a name="add-the-customdata-file"></a>Hinzufügen der CustomData-Datei

Die CustomData-Datei ist eine Textdatei, die die Dateinamenserweiterung .CustomData aufweist und XML enthält. Der Dateiname kann auf einen beliebigen Wert festgelegt werden, der für Ihre Vorlage sinnvoll ist. Der XML-Code in der CustomData-Datei weist Visual Basic an, Ihre `My`-Erweiterung einzuschließen, wenn Benutzer die Seite **Meine Erweiterungen** des Projekt-Designers in Visual Basic verwenden. Optional können Sie im XML-Code Ihrer CustomData-Datei das <`AssemblyFullName>`-Attribut hinzufügen. Dadurch wird Visual Basic angewiesen, automatisch Ihrer benutzerdefinierte `My`-Erweiterung zu installieren, wenn ein Verweis auf eine bestimmte Assembly dem Projekt hinzugefügt wird. Sie können einen beliebigen Text- oder XML-Editor verwenden, um die CustomData-Datei zu erstellen und sie dann dem komprimierten Ordner Ihrer Elementvorlage hinzufügen (ZIP-Datei).

Der folgende XML-Code zeigt beispielsweise die Inhalte einer CustomData-Datei, die die Elementvorlage dem Ordner „Meine Erweiterungen“ eines Visual Basic-Projekts hinzufügt, wenn ein Verweis auf die Microsoft.VisualBasic.PowerPacks.Vs.dll-Assembly dem Projekt hinzugefügt wird.

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

Die CustomData-Datei enthält ein <`VBMyExtensionTemplate>`-Element, das Attribute wie in der folgenden Tabelle beschrieben aufweist.

|Attribut|Beschreibung|
|---|---|
|`ID`|Erforderlich. Ein eindeutiger Bezeichner für die Erweiterung. Wenn die Erweiterung, die diesen Bezeichner aufweist, bereits dem Projekt hinzugefügt wurde, wird der Benutzer nicht dazu aufgefordert, sie noch mal hinzuzufügen.|
|`Version`|Erforderlich. Eine Versionsnummer für die Elementvorlage.|
|`AssemblyFullName`|Dies ist optional. Ein Assemblyname. Wenn ein Verweis auf diese Assembly dem Projekt hinzugefügt wird, wird der Benutzer aufgefordert, die `My`-Erweiterung aus dieser Elementvorlage hinzuzufügen.|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Fügen Sie das \<CustomDataSignature>-Element zur .vstemplate-Datei hinzu.

Sie müssen auch die VSTEMPLATE-Datei für Ihre Elementvorlage anpassen, um Ihre Visual Studio-Elementvorlage als `My`-Namespaceerweiterung zu identifizieren. Sie müssen dem `<TemplateData>`-Element ein `<CustomDataSignature>`-Element hinzufügen. Das `<CustomDataSignature>`-Element muss wie im folgenden Beispiel gezeigt den Text `Microsoft.VisualBasic.MyExtension` enthalten.

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

Sie können Dateien in einem komprimierten Ordner (ZIP-Datei) nicht direkt bearbeiten. Sie müssen die VSTEMPLATE-Datei aus dem komprimierten Ordner kopieren, sie ändern und die VSTEMPLATE-Datei im komprimierten Ordner dann durch die aktualisierte Kopie ersetzen.

Im folgenden Beispiel sehen Sie die Inhalte einer VSTEMPLATE-Datei, der das `<CustomDataSignature>`-Element hinzugefügt wurde.

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

## <a name="install-the-template"></a>Installieren der Vorlage

Zur Installation der Vorlage können Sie den komprimierten Ordner (die *ZIP*-Datei) in den Elementvorlagenordner in Visual Basic kopieren. Standardmäßig befinden sich Benutzerelementvorlagen unter *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*. Alternativ können Sie die Vorlage als Visual Studio-Installerdatei ( *.vsi*) veröffentlichen.

## <a name="see-also"></a>Siehe auch

- [Extending the My Namespace in Visual Basic (Erweitern des Namespaces „My“ in Visual Basic)](extending-the-my-namespace.md)
- [Erweitern des Visual Basic-Anwendungsmodells](extending-the-visual-basic-application-model.md)
- [Anpassen der verfügbaren Objekte in „My“](customizing-which-objects-are-available-in-my.md)
- [My-Erweiterungen-Seite im Projekt-Designer](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
