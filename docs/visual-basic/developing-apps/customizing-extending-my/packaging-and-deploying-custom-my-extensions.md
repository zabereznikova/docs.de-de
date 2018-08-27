---
title: Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 4212f58c39f63be6ba20c3b79e5d9c98d0615c5e
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931491"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>Packen und Bereitstellen von benutzerdefinierten My-Erweiterungen (Visual Basic)

Visual Basic bietet eine einfache Möglichkeit zum Bereitstellen benutzerdefinierter `My` Namespaceerweiterungen mithilfe von Visual Studio-Vorlagen. Wenn Sie eine Projektvorlage für das Erstellen Ihrer `My` Erweiterungen sind ein wesentlicher Bestandteil des neuen Projekttyps, Sie können nur einschließen, die benutzerdefinierte `My` Erweiterungscode mit dem Projekt aus, wenn Sie die Vorlage exportieren. Weitere Informationen zum Exportieren von Vorlagen finden Sie unter [Vorgehensweise: Erstellen von Projektvorlagen](/visualstudio/ide/how-to-create-project-templates).

Wenn Ihre benutzerdefinierte `My` Erweiterung befindet sich in einer einzigen Codedatei, können Sie die Datei exportieren, wie eine Elementvorlage, die Benutzer auf jede Art von Visual Basic-Projekt hinzufügen können. Sie können dann die Item-Vorlage, um zusätzliche Funktionen und Verhalten für die benutzerdefinierte Anpassen `My` -Erweiterung in Visual Basic-Projekt. Diese Funktionen umfassen Folgendes:

- Ermöglicht Benutzern das Verwalten Ihrer benutzerdefiniertes `My` -Erweiterung aus der **My-Erweiterungen** auf der Seite der Visual Basic-Projekt-Designer.

- Automatisches Hinzufügen der benutzerdefinierten `My` Erweiterung auf, wenn ein Verweis auf eine angegebene Assembly zu einem Projekt hinzugefügt wird.

- Durch das Ausblenden der `My` Erweiterung Item-Vorlage in der **Element hinzufügen** Dialogfeld, sodass es nicht in der Liste der Projektelemente enthalten ist.

In diesem Thema wird erläutert, wie Sie ein benutzerdefiniertes Paket `My` Erweiterung als ausgeblendetes Elementvorlage, die von verwaltet werden, kann die **My-Erweiterungen** auf der Seite der Visual Basic-Projekt-Designer. Die benutzerdefinierte `My` Erweiterung kann auch automatisch hinzugefügt werden, wenn ein Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird.

## <a name="create-a-my-namespace-extension"></a>Erstellen einer My-Namespaceerweiterung

Der erste Schritt beim Erstellen eines Bereitstellungspakets für eine benutzerdefinierte `My` Erweiterung ist, um die Erweiterung als eine einzelne Codedatei zu erstellen. Weitere Informationen und Anleitungen zum Erstellen eines benutzerdefinierten `My` -Erweiterung finden Sie unter [erweitern die My-Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Exportieren einer My-Namespaceerweiterung als eine Item-Vorlage

Nach dem Sie eine Codedatei, enthalten Ihre `My` Namespaceerweiterung, können Sie den Codedatei als Visual Studio-Elementvorlage exportieren. Anweisungen dazu, wie Sie eine Datei als Visual Studio-Elementvorlage exportieren, finden Sie unter [Vorgehensweise: Erstellen von Elementvorlagen](/visualstudio/ide/how-to-create-item-templates).

> [!NOTE]
> Wenn Ihre `My` Namespaceerweiterung besteht eine Abhängigkeit zu einer bestimmten Assembly, können Sie die Elementvorlage für die automatische Installation anpassen Ihrer `My` Namespaceerweiterung auf, wenn ein Verweis auf die Assembly hinzugefügt wird. Daher werden Sie der Assemblyverweis, wenn Sie die Codedatei als Visual Studio-Elementvorlage exportieren möchten.

## <a name="customize-the-item-template"></a>Die Item-Vorlage anpassen

Die Elementvorlage aus verwaltet werden können die **My-Erweiterungen** auf der Seite der Visual Basic-Projekt-Designer. Sie können auch ermöglichen, dass die Item-Vorlage automatisch hinzugefügt werden soll, wenn ein Projekt ein Verweis auf eine angegebene Assembly hinzugefügt wird. Um diese Anpassungen zu aktivieren, Sie fügen eine neue Datei mit dem Namen der CustomData-Datei und in der Vorlage aus, und der XML-Code dann ein neues Element hinzugefügt werden, in der VSTEMPLATE-Datei.

### <a name="add-the-customdata-file"></a>Die CustomData-Datei hinzufügen

Die CustomData-Datei ist eine Textdatei mit der Dateinamenerweiterung. CustomData (der Dateiname kann festgelegt werden auf einen beliebigen Wert für die Vorlage von Bedeutung), das XML enthält. Die XML-Code in die CustomData-Datei weist Visual Basic umfassen Ihre `My` Erweiterung auf, wenn der Benutzer die **My-Erweiterungen** auf der Seite der Visual Basic-Projekt-Designer. Sie können optional auch hinzufügen, die <`AssemblyFullName>` der CustomData-Datei XML-Attribut. Dies weist Visual Basic für die automatische Installation von benutzerdefinierten `My` Erweiterung auf, wenn ein Verweis auf eine bestimmte Assembly wird dem Projekt hinzugefügt. Sie können jeden beliebigen Text- oder XML-Editor verwenden, um die CustomData-Datei zu erstellen, und fügen Sie es auf der Elementvorlage komprimierten Ordner (ZIP-Datei).

Das folgende XML zeigt beispielsweise den Inhalt einer CustomData-Datei, die das Vorlagenelement in den Ordner My-Erweiterungen ein Visual Basic-Projekt, wenn ein Verweis auf die Assembly Microsoft.VisualBasic.PowerPacks.Vs.dll hinzufügen wird dem Projekt hinzugefügt.

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

Die CustomData-Datei enthält ein <`VBMyExtensionTemplate>` -Element, das über in der folgenden Tabelle aufgeführten Attribute verfügt.

|Attribut|Beschreibung|
|---|---|
|`ID`|Erforderlich. Ein eindeutiger Bezeichner für die Erweiterung. Wenn die Erweiterung, die diese ID muss dem Projekt bereits hinzugefügt wurde, wird der Benutzer nicht aufgefordert werden, es erneut hinzu.|
|`Version`|Erforderlich. Eine Versionsnummer für die Elementvorlage.|
|`AssemblyFullName`|Dies ist optional. Ein Assemblyname. Wenn das Projekt ein Verweis auf diese Assembly hinzugefügt wird, die Benutzer werden aufgefordert, Hinzufügen der `My` Erweiterung aus dieser Elementvorlage.|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Hinzufügen der \<CustomDataSignature >-Element der VSTEMPLATE-Datei

Identifizieren Sie die Visual Studio-Elementvorlage als eine `My` Namespaceerweiterung, müssen Sie auch die VSTEMPLATE-Datei für die Item-Vorlage ändern. Müssen Sie hinzufügen, eine `<CustomDataSignature>` Element, das `<TemplateData>` Element. Die `<CustomDataSignature>` -Element muss den Text enthalten `Microsoft.VisualBasic.MyExtension`, wie im folgenden Beispiel gezeigt.

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

Sie können keine Dateien in einem komprimierten Ordner (ZIP-Datei) nicht direkt ändern. Sie müssen die VSTEMPLATE-Datei aus dem komprimierten Ordner kopieren, sie ändern und Ersetzen Sie die VSTEMPLATE-Datei in den komprimierten Ordner durch die aktualisierte Version.

Das folgende Beispiel zeigt den Inhalt einer VSTEMPLATE-Datei, die die `<CustomDataSignature>` hinzugefügte Element.

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

Um die Vorlage zu installieren, können Sie den komprimierten Ordner kopieren (*ZIP* Datei) zum Ordner "Visual Basic Item Templates". Standardmäßig befinden sich Benutzerelementvorlagen im *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*. Alternativ können Sie die Vorlage als eine Visual Studio-Installer veröffentlichen (*VSI*) Datei.

## <a name="see-also"></a>Siehe auch

- [Extending the My Namespace in Visual Basic (Erweitern des Namespaces „My“ in Visual Basic)](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [My-Erweiterungen-Seite im Projekt-Designer](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
