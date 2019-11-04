---
title: Festlegen von Assemblyattributen
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- assembly binding, attributes
- assembly manifest, attributes
ms.assetid: 36a98a81-b5b5-4c19-912a-11f91eff7f4e
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: fe003a6c74da59c1cb47a0f12a8597143916e320
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138636"
---
# <a name="set-assembly-attributes"></a>Festlegen von Assemblyattributen

Assemblyattribute sind Werte, die Informationen zu einer Assembly bereitstellen. Die Attribute sind in die folgenden Gruppen von Informationen unterteilt:

- Attribute für Assemblyidentitäten

- Informationsattribute

- Attribute für Assemblymanifeste.

- Attribute für starke Namen

## <a name="assembly-identity-attributes"></a>Attribute für Assemblyidentitäten

Drei Attribute bestimmen zusammen mit einem starken Namen (falls zutreffend) die Identität einer Assembly: "name", "version" und "culture". Diese Attribute bilden den vollständigen Namen der Assembly und sind erforderlich, wenn im Code auf die Assembly verwiesen wird. Mit Attributen können die Version und Kultur einer Assembly festgelegt werden. Der Compiler oder der [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) legt beim Erstellen der Assembly den Namenswert auf Grundlage der Datei fest, die das Assemblymanifest enthält.

In der folgenden Tabelle werden das version- und das culture-Attribut beschrieben.

|Attribut für Assemblyidentität|BESCHREIBUNG|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyCultureAttribute>|Ein aufgelistetes Feld, das die von der Assembly unterstützte Kultur angibt. Eine Assembly kann auch eine Kulturunabhängigkeit angeben. In diesem Fall enthält sie die Ressourcen für die Standardkultur. **Hinweis**:  Die Runtime behandelt jede Assembly, für die das culture-Attribut nicht auf NULL festgelegt ist, als Satellitenassembly. Solche Assemblys unterliegen den Bindungsregeln für Satellitenassemblys. Weitere Informationen finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../framework/deployment/how-the-runtime-locates-assemblies.md).|
|<xref:System.Reflection.AssemblyFlagsAttribute>|Ein Wert, der Assemblyattribute festlegt, etwa ob die Assembly parallel ausgeführt werden kann.|
|<xref:System.Reflection.AssemblyVersionAttribute>|Ein numerischer Wert mit dem Format *Haupt*.*Neben*.*Build*.*Revision* (z. B. 2.4.0.0). Common Language Runtime verwendet diesen Wert zum Durchführen von Bindungsvorgängen in Assemblys mit der Eigenschaft "Starker Name". **Hinweis**:  Wenn das <xref:System.Reflection.AssemblyInformationalVersionAttribute>-Attribut nicht auf eine Assembly angewendet wird, wird die Versionsnummer, die vom <xref:System.Reflection.AssemblyVersionAttribute>-Attribut angegeben wird, von den Eigenschaften <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> verwendet.|

Im folgenden Codebeispiel wird veranschaulicht, wie das version- und das culture-Attribut auf eine Assembly angewendet werden.

```cpp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")];
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")];
```

```csharp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")]
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")]
```

```vb
' Set version number for the assembly.
<Assembly:AssemblyVersionAttribute("4.3.2.1")>
' Set culture as German.
<Assembly:AssemblyCultureAttribute("de")>
```

## <a name="informational-attributes"></a>Informationsattribute

Mit Informationsattributen können Sie zusätzliche Firmen- oder Produktinformationen für eine Assembly bereitstellen. Die folgende Tabelle beschreibt die verschiedenen Informationsattribute, die auf eine Assembly angewendet werden können.

|Informationsattribut|BESCHREIBUNG|
|-----------------------------|-----------------|
|<xref:System.Reflection.AssemblyCompanyAttribute>|Ein Zeichenfolgenwert, der einen Firmennamen angibt.|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Ein Zeichenfolgenwert, der Copyright-Informationen angibt.|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Ein Zeichenfolgenwert, der die Win32-Dateiversionsnummer angibt. Dies ist normalerweise standardmäßig die Assemblyversion.|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Ein Zeichenfolgenwert, der Versionsinformationen angibt, die zur Laufzeit nicht verwendet werden (zum Beispiel die vollständige Produktversionsnummer). **Hinweis**:  Wenn dieses Attribut auf eine Assembly angewendet wird, kann die davon angegebene Zeichenfolge zur Laufzeit mithilfe der <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>-Eigenschaft abgerufen werden. Diese Zeichenfolge wird auch im von den Eigenschaften <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> bereitgestellten Pfad und Registrierungsschlüssel verwendet.|
|<xref:System.Reflection.AssemblyProductAttribute>|Ein Zeichenfolgenwert, der Produktinformationen angibt.|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Ein Zeichenfolgenwert, der Markeninformationen angibt.|

Diese Attribute können auf der Windows-Eigenschaftenseite der Assembly angezeigt werden, oder sie können mithilfe der **/win32res** -Compileroption überschrieben werden, um Ihre eigene Win32-Ressourcendatei anzugeben.

## <a name="assembly-manifest-attributes"></a>Attribute für Assemblymanifeste.

Mit Attributen für Assemblymanifeste können Informationen im Assemblymanifest angegeben werden, einschließlich Titel, Beschreibung, Standardalias und Konfiguration. In der folgenden Tabelle werden die Attribute für Assemblymanifeste beschrieben.

|Attribut für Assemblymanifeste|BESCHREIBUNG|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Ein Zeichenfolgenwert, der die Assemblykonfiguration angibt, beispielsweise "Einzelhandel" oder "Debuggen". Dieser Wert wird zur Laufzeit nicht verwendet.|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Ein Zeichenfolgenwert, der einen Standardalias angibt, der von Assemblys mit einem Verweis verwendet werden soll. Dieser Wert stellt einen Anzeigenamen zur Verfügung, wenn der eigentliche Name der Assembly nicht angezeigt wird (zum Beispiel ein GUID-Wert). Dieser Wert kann auch als Kurzform des vollen Assemblynamens verwendet werden.|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Ein Zeichenfolgenwert, der eine kurze Beschreibung angibt, die Natur und Zweck der Assembly zusammenfasst.|
|<xref:System.Reflection.AssemblyTitleAttribute>|Ein Zeichenfolgenwert, der einen Anzeigenamen für die Assembly angibt. Beispielsweise kann eine Assembly mit dem Namen *comdlg* den Titel „Microsoft Common Dialog Control“ (Allgemeines Microsoft-Dialogsteuerelement) haben.|

## <a name="strong-name-attributes"></a>Attribute für starke Namen

Sie können Attribute für starke Namen verwenden, um einen starken Namen für eine Assembly festzulegen. In der folgenden Tabelle werden die Attribute für starke Namen beschrieben.

|Attribut für starke Namen|BESCHREIBUNG|
|----------------------------|-----------------|
|<xref:System.Reflection.AssemblyDelaySignAttribute>|Ein boolescher Wert, der angibt, dass die verzögerte Signierung verwendet wird|
|<xref:System.Reflection.AssemblyKeyFileAttribute>|Ein Zeichenfolgenwert, der den Namen der Datei angibt, die entweder den öffentlichen Schlüssel (bei verzögerter Signierung) oder öffentliche und private Schlüssel enthält, die an den Konstruktor dieses Attributs als Parameter übergeben werden. Beachten Sie, dass der Dateiname relativ zum Pfad der Ausgabedatei ist (die *EXE*- oder *DLL*-Datei) und nicht zum Pfad der Quelldatei.|
|<xref:System.Reflection.AssemblyKeyNameAttribute>|Zeigt den Schlüsselcontainer an, der das Schlüsselpaar enthält, das an den Konstruktor dieses Attributs als Parameter übergeben wurde.|

Das folgende Codebeispiel zeigt die Attribute, die angewendet werden, wenn mithilfe der verzögerten Signierung eine Assembly mit starkem Namen mit einer Datei des öffentlichen Schlüssels *myKey.snk* erstellt wird.

```cpp
[assembly:AssemblyKeyFileAttribute("myKey.snk")];
[assembly:AssemblyDelaySignAttribute(true)];
```

```csharp
[assembly:AssemblyKeyFileAttribute("myKey.snk")]
[assembly:AssemblyDelaySignAttribute(true)]
```

```vb
<Assembly:AssemblyKeyFileAttribute("myKey.snk")>
<Assembly:AssemblyDelaySignAttribute(True)>
```

## <a name="see-also"></a>Siehe auch

- [Erstellen von Assemblys](create.md)
- [Programmieren mit Assemblys](program.md)
