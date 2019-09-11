---
title: EDM-Generator (EdmGen.exe)
ms.date: 03/30/2017
ms.assetid: fe8297a1-1fc3-48ce-8eeb-f70f63f857aa
ms.openlocfilehash: 82166782e25cb7a7ea23fe7faf7a30cb0e68d631
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854720"
---
# <a name="edm-generator-edmgenexe"></a>EDM-Generator (EdmGen.exe)

EdmGen. exe ist ein Befehlszeilen Tool, das zum Arbeiten mit Entity Framework Modell-und Zuordnungs Dateien verwendet wird. Mit dem Tool EdmGen.exe können folgende Aufgaben ausgeführt werden:

- Stellen Sie eine Verbindung mit einer Datenquelle her, indem Sie eine Datenquelle – spezifische .NET Framework Datenanbieter) verwenden, und generieren Sie das konzeptionelle Modell (CSDL), das Speichermodell (SSDL) und die Mapping-Dateien (. MSL), die vom Entity Framework verwendet werden. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie EdmGen. exe, um die Modell-und](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)Zuordnungsdateien zu generieren.

- Überprüfen eines bestehenden Modells. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie zum Überprüfen von Modell-und Zuordnungsdateien](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)EdmGen. exe.

- Erstellen einer C#- oder Visual Basic-Codedatei, die die Objektklassen enthält, die aus einer Datei für das konzeptionelle Modell (CSDL) generiert wurden. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie "EdmGen. exe" zum Generieren von](how-to-use-edmgen-exe-to-generate-object-layer-code.md)objektebenencode.

- Generieren einer C#- oder Visual Basic-Codedatei, die die vorab generierten Sichten für ein vorhandenes Modell enthält. Weitere Informationen finden [Sie unter Vorgehensweise: Generieren Sie vorab Sichten, um die Abfrage](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))Leistung zu verbessern.

Das Tool "EdmGen. exe" wird im .NET Framework Verzeichnis installiert. Dieses befindet sich meist unter C:\Windows\Microsoft.NET\Framework\v4.0. Bei 64-Bit-Systemen befindet es sich unter C:\Windows\Microsoft.NET\Framework64\v4.0. Sie können auch über die Visual Studio-Eingabeaufforderung auf das Tool "EdmGen. exe" zugreifen (Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Microsoft Visual Studio 2010**, zeigen Sie auf **Visual Studio-Tools**, und klicken Sie dann auf **Visual Studio 2010. Eingabeaufforderung**).

## <a name="syntax"></a>Syntax

```
EdmGen /mode:choice [options]
```

## <a name="mode"></a>Modus

Wenn Sie das Tool EdmGen.exe verwenden, müssen Sie einen der folgenden Modi angeben.

|Modus|Beschreibung|
|----------|-----------------|
|`/mode:ValidateArtifacts`|Überprüft die CSDL-, SSDL- und MSL-Dateien und zeigt alle Fehler und Warnungen an.<br /><br /> Diese Option erfordert mindestens eines der Argumente `/inssdl` oder `/incsdl`. Wenn `/inmsl` angegeben wird, sind auch die Argumente `/inssdl` und `/incsdl` erforderlich.|
|`/mode:FullGeneration`|Verwendet die in der `/connectionstring`-Option angegebenen Informationen zur Datenbankverbindung, und erstellt die CSDL-, SSDL-, .MSL-, Objektebenen- und Sichtdateien.<br /><br /> Diese Option erfordert ein `/connectionstring`-Argument sowie entweder ein `/project`-Argument oder die Argumente `/outssdl`, `/outcsdl`, `/outmsdl`, `/outobjectlayer`, `/outviews`, `/namespace` und `/entitycontainer`.|
|`/mode:FromSSDLGeneration`|Generiert CSDL- und MSL-Dateien, Quellcode und Sichten mithilfe der angegebenen SSDL-Datei.<br /><br /> Diese Option erfordert das `/inssdl`-Argument und entweder ein `/project`-Argument oder die Argumente `/outcsdl`, `/outmsl`, `/outobjectlayer`, `/outviews`, `/namespace,` und `/entitycontainer`.|
|`/mode:EntityClassGeneration`|Erstellt eine Quellcodedatei, die die mithilfe der CSDL-Datei generierten Klassen enthält.<br /><br /> Diese Option erfordert das `/incsdl`-Argument sowie das `/project`-Argument oder das `/outobjectlayer`-Argument. Das `/language`-Argument ist optional.|
|`/mode:ViewGeneration`|Erstellt eine Quellcodedatei, die die aus den CSDL-, SSDL- und MSL-Dateien generierten Sichten enthält.<br /><br /> Diese Option erfordert die Argumente `/inssdl`, `/incsdl` und `/inmsl,` sowie entweder das `/project`-Argument oder das `/outviews`-Argument. Das `/language`-Argument ist optional.|

## <a name="options"></a>Optionen

|Option|Beschreibung|
|------------|-----------------|
|`/p[roject]:`\<string>|Gibt den zu verwendenden Projektnamen an. Der Projektname wird für die standardmäßige Namespaceeinstellung, die Namen der Modell- und Zuordnungsdateien, den Namen der Objektquelldatei und den Namen der Quelldatei für das Generieren von Ansichten verwendet. Der Entitätencontainername \<wird auf Projekt > Kontext festgelegt.|
|`/prov[ider]:`\<string>|Der Name des .NET Framework-Datenanbieters zum Erstellen der Speichermodelldatei (SSDL). Der Standardanbieter ist der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>).|
|`/c[onnectionstring]:`\<Verbindungs Zeichenfolge >|Gibt die Zeichenfolge an, die verwendet wird, um eine Verbindung mit der Datenquelle herzustellen.|
|`/incsdl:`\<file>|Gibt die CSDL-Datei oder ein Verzeichnis an, in dem sich die CSDL-Dateien befinden. Dieses Argument kann mehrmals angegeben werden, damit Sie mehrere Verzeichnisse oder CSDL-Dateien angeben können. Das Angeben mehrerer Verzeichnisse ist beim Erstellen von Klassen (`/mode:EntityClassGeneration`) oder Sichten (`/mode:ViewGeneration`) hilfreich, wenn das konzeptionelle Modell in mehrere Dateien aufgeteilt ist. Dies kann auch nützlich sein, wenn Sie mehrere Modelle (`/mode:ValidateArtifacts`) überprüfen möchten.|
|`/refcsdl:`\<file>|Gibt die zusätzliche CSDL-Datei bzw. -Dateien an, die verwendet werden, um die Verweise in der CSDL-Quelldatei aufzulösen. (Die CSDL-Quelldatei ist die mit der `/incsdl`-Option angegebene Datei). Die `/refcsdl`-Datei enthält Typen, von denen die CSDL-Quelldatei abhängt. Dieses Argument kann mehrmals angegeben werden.|
|`/inmsl:`\<file>|Gibt die MSL-Datei oder ein Verzeichnis an, in dem sich die MSL-Dateien befinden. Dieses Argument kann mehrmals angegeben werden, um mehrere Verzeichnisse oder MSL-Dateien anzugeben. Das Angeben mehrerer Dateien ist beim Erstellen von Sichten (`/mode:ViewGeneration`) hilfreich, wenn das konzeptionelle Modell in mehrere Dateien aufgeteilt ist. Dies kann auch nützlich sein, wenn Sie mehrere Modelle (`/mode:ValidateArtifacts`) überprüfen möchten.|
|`/inssdl:`\<file>|Gibt die SSDL-Datei oder ein Verzeichnis an, in dem sich die SSDL-Datei befindet. Dieses Argument kann mehrmals angegeben werden, damit Sie mehrere Verzeichnisse oder SSDL-Dateien angeben können. Dies kann auch nützlich sein, wenn Sie mehrere Modelle `(/mode:ValidateArtifacts)` überprüfen möchten.|
|`/outcsdl:`\<file>|Gibt den Namen der CSDL-Datei an, die erstellt wird.|
|`/outmsl:`\<file>|Gibt den Namen der MSL-Datei an, die erstellt wird.|
|`/outssdl:`\<file>|Gibt den Namen der SSDL-Datei an, die erstellt wird.|
|`/outobjectlayer:`\<file>|Gibt den Namen der Quellcodedatei an, die die mit der CSDL-Datei generierten Objekte enthält.|
|`/outviews:`\<file>|Gibt den Namen der Quellcodedatei an, die die generierten Sichten enthält.|
|`/language:`[VB&#124;CSharp]|Gibt die Sprache für die erstellten Quellcodedateien an. Die Standardsprache ist C#.|
|`/namespace:`\<string>|Gibt den zu verwendenden Namespace für das Modell an. Der Namespace wird beim Ausführen von `/mode:FullGeneration` oder `/mode:FromSSDLGeneration` in der CSDL-Datei festgelegt. Beim Ausführen `/mode:EntityClassGeneration` wird der Namespace nicht verwendet.|
|`/entitycontainer:`\<string>|Gibt den Namen an, der dem `<EntityContainer>`-Element in den generierten Modell- und Zuordnungsdateien hinzugefügt wird.|
|`/pl[uralize]`|Wendet für das Englische geltende Regeln für Singular- und Pluralbildung auf die Namen von `Entity`, `EntitySet` und `NavigationProperty` im konzeptionellen Modell an. Diese Option führt die folgenden Aktionen aus:<br /><br /> -Alle `EntityType` Namen als Singular festlegen.<br />: Macht alle `EntitySet` Namen als Plural.<br />-Für jeden `NavigationProperty` , der höchstens eine Entität zurückgibt, legen Sie den Namen als Singular fest.<br />-Für jeden `NavigationProperty` , der mehr als eine Entität zurückgibt, geben Sie den Namen Plural.|
|`/SuppressForeignKeyProperties or /nofk`|Verhindert, dass Fremdschlüsselspalten als skalare Eigenschaften von Entitätstypen im konzeptionellen Modell verfügbar gemacht werden.|
|`/help` oder `?`|Zeigt Befehlssyntax und Optionen für das Tool an.|
|`/nologo`|Unterdrückt die Anzeige der Copyrightmeldung.|
|`/targetversion:` \<string>|Die Version von .NET Framework, die zum Kompilieren des generierten Codes verwendet wird. Unterstützt werden Version 4 und 4.5. Der Standardwert ist 4.|

## <a name="in-this-section"></a>In diesem Abschnitt

[Vorgehensweise: Verwenden von "EdmGen. exe" zum Generieren der Modell-und Zuordnungsdateien](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)

[Vorgehensweise: Verwenden von "EdmGen. exe" zum Generieren von objektebenencode](how-to-use-edmgen-exe-to-generate-object-layer-code.md)

[Vorgehensweise: Verwenden von EdmGen. exe zum Überprüfen von Modell-und Zuordnungsdateien](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)

## <a name="see-also"></a>Siehe auch

- [ADO.NET-Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Entity Data Model](../entity-data-model.md)
- [CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)](./language-reference/csdl-ssdl-and-msl-specifications.md)
