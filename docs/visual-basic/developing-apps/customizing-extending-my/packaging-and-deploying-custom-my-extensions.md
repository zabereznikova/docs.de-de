---
title: Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: a2e2a6705fb3d8d4424d46d96bbf49b41e1414af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330261"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)

Visual Basic bietet eine einfache Möglichkeit zum Bereitstellen Ihrer benutzerdefinierten `My`-Namespace Erweiterungen mithilfe von Visual Studio-Vorlagen. Wenn Sie eine Projektvorlage erstellen, für die ihre `My` Erweiterungen ein wesentlicher Bestandteil des neuen Projekt Typs sind, können Sie den benutzerdefinierten `My` Erweiterungs Code beim Exportieren der Vorlage einfach mit dem Projekt einschließen. Weitere Informationen zum Exportieren von Projektvorlagen finden Sie unter Gewusst [wie: Erstellen von Projektvorlagen](/visualstudio/ide/how-to-create-project-templates).

Wenn sich die Erweiterung des benutzerdefinierten `My` in einer einzelnen Codedatei befindet, können Sie die Datei als Element Vorlage exportieren, die Benutzer zu beliebigen Visual Basic Projekttypen hinzufügen können. Anschließend können Sie die Element Vorlage anpassen, um zusätzliche Funktionen und das Verhalten für die benutzerdefinierte `My` Erweiterung in einem Visual Basic-Projekt zu aktivieren. Diese Funktionen umfassen Folgendes:

- Ermöglicht Benutzern das Verwalten Ihrer benutzerdefinierten `My` Erweiterung auf der Seite " **Meine Erweiterungen** " des Visual Basic Projekt-Designers.

- Automatisches Hinzufügen der benutzerdefinierten `My` Erweiterung, wenn ein Verweis auf eine angegebene Assembly einem Projekt hinzugefügt wird.

- Ausblenden der Element Vorlage für `My` Erweiterungen im Dialogfeld **Element hinzufügen** , sodass Sie nicht in der Liste der Projekt Elemente enthalten ist.

In diesem Thema wird erläutert, wie Sie eine benutzerdefinierte `My` Erweiterung als ausgeblendete Element Vorlage Verpacken, die auf der Seite **Meine Erweiterungen** des Visual Basic Projekt-Designers verwaltet werden kann. Die Erweiterung für benutzerdefinierte `My` kann auch automatisch hinzugefügt werden, wenn einem Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.

## <a name="create-a-my-namespace-extension"></a>Erstellen einer My-Namespace Erweiterung

Der erste Schritt beim Erstellen eines Bereitstellungs Pakets für eine benutzerdefinierte `My` Erweiterung besteht darin, die Erweiterung als einzelne Codedatei zu erstellen. Ausführliche Informationen und Anleitungen zum Erstellen einer benutzerdefinierten `My` Erweiterung finden Sie unter [Erweitern des My-Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Exportieren einer My-Namespace Erweiterung als Element Vorlage

Nachdem Sie eine Codedatei mit der Erweiterung für den `My`-Namespace erstellt haben, können Sie die Codedatei als Visual Studio-Element Vorlage exportieren. Anweisungen zum Exportieren einer Datei als Visual Studio-Element Vorlage finden Sie unter Gewusst [wie: Erstellen von Element Vorlagen](/visualstudio/ide/how-to-create-item-templates).

> [!NOTE]
> Wenn die `My`-Namespace Erweiterung von einer bestimmten Assembly abhängig ist, können Sie die Element Vorlage so anpassen, dass Ihre `My`-Namespace Erweiterung automatisch installiert wird, wenn ein Verweis auf diese Assembly hinzugefügt wird. Daher sollten Sie diesen Assemblyverweis ausschließen, wenn Sie die Codedatei als Visual Studio-Element Vorlage exportieren.

## <a name="customize-the-item-template"></a>Anpassen der Element Vorlage

Sie können die Verwaltung der Element Vorlage auf der Seite **Meine Erweiterungen** des Visual Basic Projekt-Designers aktivieren. Sie können auch aktivieren, dass die Element Vorlage automatisch hinzugefügt wird, wenn ein Verweis auf eine angegebene Assembly einem Projekt hinzugefügt wird. Um diese Anpassungen zu aktivieren, fügen Sie der Vorlage eine neue Datei (CustomData-Datei) hinzu, und fügen Sie dann dem XML-Code in der VSTEMPLATE-Datei ein neues Element hinzu.

### <a name="add-the-customdata-file"></a>Hinzufügen der CustomData-Datei

Die CustomData-Datei ist eine Textdatei mit der Dateinamenerweiterung. CustomData (der Dateiname kann auf einen beliebigen Wert festgelegt werden, der für Ihre Vorlage sinnvoll ist) und der XML enthält. Der XML-Code in der Datei "CustomData" weist Visual Basic an, die `My` Erweiterung einzuschließen, wenn Benutzer die Seite " **Meine Erweiterungen** " des Visual Basic Projekt-Designers verwenden. Optional können Sie das <`AssemblyFullName>`-Attribut zu ihrer CustomData-Datei-XML-Datei hinzufügen. Dies weist Visual Basic an, automatisch Ihre benutzerdefinierte `My` Erweiterung zu installieren, wenn dem Projekt ein Verweis auf eine bestimmte Assembly hinzugefügt wird. Sie können einen beliebigen Text-Editor oder XML-Editor verwenden, um die CustomData-Datei zu erstellen, und Sie dann dem komprimierten Ordner der Element Vorlage (ZIP-Datei) hinzufügen.

Der folgende XML-Code zeigt z. b. den Inhalt einer CustomData-Datei, die das Vorlagen Element dem Ordner "Meine Erweiterungen" eines Visual Basic Projekts hinzufügt, wenn dem Projekt ein Verweis auf die Assembly "Microsoft. VisualBasic. PowerPacks. vs. dll" hinzugefügt wird.

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

Die CustomData-Datei enthält eine <`VBMyExtensionTemplate>`-Element, das über Attribute verfügt, wie in der folgenden Tabelle aufgeführt.

|Attribut|Beschreibung|
|---|---|
|`ID`|Erforderlich Ein eindeutiger Bezeichner für die Erweiterung. Wenn die Erweiterung mit dieser ID dem Projekt bereits hinzugefügt wurde, wird der Benutzer nicht aufgefordert, ihn erneut hinzuzufügen.|
|`Version`|Erforderlich Eine Versionsnummer für die Element Vorlage.|
|`AssemblyFullName`|Optional. Ein Assemblyname. Wenn dem Projekt ein Verweis auf diese Assembly hinzugefügt wird, wird der Benutzer aufgefordert, die `My` Erweiterung aus dieser Element Vorlage hinzuzufügen.|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Fügen Sie der VSTEMPLATE-Datei das \<CustomDataSignature >-Element hinzu.

Um die Visual Studio-Element Vorlage als `My`-Namespace Erweiterung zu identifizieren, müssen Sie auch die VSTEMPLATE-Datei für die Element Vorlage ändern. Sie müssen dem `<TemplateData>`-Element ein `<CustomDataSignature>`-Element hinzufügen. Das `<CustomDataSignature>`-Element muss den Text `Microsoft.VisualBasic.MyExtension`enthalten, wie im folgenden Beispiel gezeigt.

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

Dateien in einem komprimierten Ordner (ZIP-Datei) können nicht direkt geändert werden. Kopieren Sie die VSTEMPLATE-Datei aus dem komprimierten Ordner, ändern Sie Sie, und ersetzen Sie dann die VSTEMPLATE-Datei im komprimierten Ordner durch die aktualisierte Kopie.

Das folgende Beispiel zeigt den Inhalt einer VSTEMPLATE-Datei, der das `<CustomDataSignature>`-Element hinzugefügt wurde.

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

Zum Installieren der Vorlage können Sie den komprimierten Ordner (*ZIP* -Datei) in den Ordner "Visual Basic Element Vorlagen" kopieren. Standardmäßig befinden sich Benutzer Element Vorlagen in *%USERPROFILE%\Documents\Visual Studio \<Version\>\templates\itemtemplates\visual Basic*. Alternativ können Sie die Vorlage als Visual Studio-Installer Datei ( *. vsi*) veröffentlichen.

## <a name="see-also"></a>Siehe auch

- [Extending the My Namespace in Visual Basic (Erweitern des Namespaces „My“ in Visual Basic)](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [My-Erweiterungen-Seite im Projekt-Designer](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
