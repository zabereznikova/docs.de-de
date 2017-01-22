---
title: project.json-Verweis
description: project.json-Verweis
keywords: .NET, .NET Core, project.json
author: aL3891
ms.author: mairaw
ms.date: 12/21/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 3aef32bd-ee2a-4e24-80f8-a2b615e0336d
translationtype: Human Translation
ms.sourcegitcommit: 4023c5ec72055fee78863a43b60989e1eb34fb22
ms.openlocfilehash: 68b152cda54b5356dce48f4a8330b2ecb9c9d2e0

---

# <a name="projectjson-reference"></a>project.json-Verweis

Die Datei „project.json“ wird auf Projekten unter .NET Core verwendet, um Projektmetadaten, Kompilierungsinformationen und Abhängigkeiten zu definieren. In diesem Referenzthema finden Sie die Liste aller Eigenschaften, die Sie in der Datei „project.json“ definieren können.

> [!NOTE]
> Die .NET Core-Tools werden in einer zukünftigen Version von „project.json“ zu MSBuild-basierten Projekten verschoben. Es wird empfohlen, weiterhin „project.json“-Dateien für neue Projekte von .NET Core zu verwenden, da es einen Pfad geben wird, um Ihr Projekt zu MSBuild zu konvertieren, wenn die Tools veröffentlicht werden.
>
> Weitere Informationen finden Sie im Beitrag [Changes to project.json (Änderungen in „project.json“)](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) im .NET-Blog und im Thema [Using MSBuild to build .NET Core projects (.NET Core-Projekte mit MSBuild erstellen)](../tutorials/target-dotnetcore-with-msbuild.md).

## <a name="overview"></a>Übersicht

```
{
    "name": String,
    "version": String,
    "description": String,
    "copyright": String,
    "title": String,
    "entryPoint": String,
    "testRunner": String,
    "authors": String[],
    "language": String,
    "embedInteropTypes": Boolean,
    "preprocess": String or String[],
    "shared": String or String[],
    "dependencies": Object {
        version: String,
        type: String,
        target: String,
        include: String,
        exclude: String,
        suppressParent: String
    },
    "tools": Object,
    "scripts": Object,
    "buildOptions": Object {
        "define": String[],
        "nowarn": String[],
        "additionalArguments": String[],
        "warningsAsErrors": Boolean,
        "allowUnsafe": Boolean,
        "emitEntryPoint": Boolean,
        "optimize": Boolean,
        "platform": String,
        "languageVersion": String,
        "keyFile": String,
        "delaySign": Boolean,
        "publicSign": Boolean,
        "debugType": String,
        "xmlDoc": Boolean,
        "preserveCompilationContext": Boolean,
        "outputName": String,
        "compilerName": String,
        "compile": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        },
        "embed": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        },
        "copyToOutput": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        }
    },
    "publishOptions": Object {
        "include": String or String[],
        "exclude": String or String[],
        "includeFiles": String or String[],
        "excludeFiles": String or String[],
        "builtIns": Object,
        "mappings": Object
    },
    "runtimeOptions": Object {
        "configProperties": Object {
            "System.GC.Server": Boolean,
            "System.GC.Concurrent": Boolean,
            "System.GC.RetainVM": Boolean,
            "System.Threading.ThreadPool.MinThreads": Integer,
            "System.Threading.ThreadPool.MaxThreads": Integer
        },
        "framework": Object {
            "name": String,
            "version": String,
        },
        "applyPatches": Boolean
    },
    "packOptions": Object {
        "summary": String,
        "tags": String[],
        "owners": String[],
        "releaseNotes": String,
        "iconUrl": String,
        "projectUrl": String,
        "licenseUrl": String,
        "requireLicenseAcceptance": Boolean,
        "repository": Object {
            "type": String,
            "url": String
        },
        "files": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        }
    },
    "analyzerOptions": Object {
        "languageId": String
    },
    "configurations": Object,
    "frameworks": Object {
        "dependencies": Object {
            version: String,
            type: String,
            target: String,
            include: String,
            exclude: String,
            suppressParent: String
        },        
        "frameworkAssemblies": Object,
        "wrappedProject": String,
        "bin": Object {
            assembly: String
        }
    },
    "runtimes": Object,
    "userSecretsId": String
}
```

## <a name="name"></a>Name
Typ: Zeichenfolge

Der Name des Projekts, der sowohl für den Namen der Assembly als auch für den Namen des Pakets verwendet wird. Der Name des Ordners der obersten Ebene wird verwendet, wenn diese Eigenschaft nicht angegeben wird.

Zum Beispiel:

```json
{
    "name": "MyLibrary"
}
```

## <a name="version"></a>Version
Typ: Zeichenfolge

Die [Semver](http://semver.org/spec/v1.0.0.html)-Version des Projekts. Wird auch für das NuGet-Paket verwendet.

Zum Beispiel:

```json
{
    "version": "1.0.0-*"
}
```

## <a name="description"></a>Beschreibung
Typ: Zeichenfolge

Eine längere Beschreibung des Projekts. In den Assemblyeigenschaften verwendet.

Zum Beispiel:

```json
{
    "description": "This is my library and it's really great!"
}
```

## <a name="copyright"></a>Copyright
Typ: Zeichenfolge

Die Urheberrechtsinformationen des Projekts. In den Assemblyeigenschaften verwendet.

Zum Beispiel:

```json
{
    "copyright": "Fabrikam 2016"
}
```

## <a name="title"></a>Titel
Typ: Zeichenfolge

Der Anzeigename des Projekts kann Leerzeichen und Sonderzeichen enthalten, die beim Verwenden der Eigenschaft `name` nicht zulässig sind. In den Assemblyeigenschaften verwendet.

Zum Beispiel:

```json
{
    "title": "My Library"
}
```

## <a name="entrypoint"></a>entryPoint
Typ: Zeichenfolge

Die Einstiegspunktmethode für das Projekt. `Main` standardmäßig.

Beispiel:

```json
{
    "entryPoint": "ADifferentMethod"
}
```
    
## <a name="testrunner"></a>testRunner
Typ: Zeichenfolge

Der Name des Test Runners, z.B. [NUnit](http://nunit.org/) oder [xUnit](http://xunit.github.io/), der für dieses Projekt zu verwenden ist. Diese Einstellung markiert das Projekt auch als ein Testprojekt.

Zum Beispiel:

```json
{
    "testRunner": "NUnit"
}
```

## <a name="authors"></a>authors
Typ: Zeichenfolge[]

Ein Array von Zeichenfolgen mit den Namen der Autoren des Projekts.

Zum Beispiel:

```json
{
    "authors": ["Anne", "Bob"]
}
```

## <a name="language"></a>language
Typ: Zeichenfolge

Die (natürliche) Sprache des Projekts. Entspricht dem Compilerargument „neutrale Sprache“.

Zum Beispiel:

```json
{
    "language": "en-US"
}
```

## <a name="embedinteroptypes"></a>embedInteropTypes
Typ: Boolesch

`true` zum Einbetten von COM-Interop-Typen in die Assembly, andernfalls `false`. 

Beispiel:

```json
{
    "embedInteropTypes": true
}
```

## <a name="preprocess"></a>preprocess
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster

Gibt an, welche Daten in der Vorabverarbeitung enthalten sind.

Zum Beispiel:

```json
{
    "preprocess": "compiler/preprocess/**/*.cs"
}
```

## <a name="shared"></a>Freigegeben
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster

Gibt an, welche Dateien freigegeben werden. Wird beim Exportieren von Bibliotheken verwendet.

Zum Beispiel:

```json
{
    "shared": "shared/**/*.cs"
}
```

## <a name="dependencies"></a>Abhängigkeiten
Typ: Objekt

Ein Objekt, das die Abhängigkeiten des Projekts definiert. Jeder Schlüssel dieses Objekts ist der Name eines Pakets, und jeder Wert enthält Versionsinformationen.
Weitere Informationen finden Sie im Artikel [Dependency resolution (Abhängigkeitsauflösung)](https://docs.nuget.org/ndocs/consume-packages/dependency-resolution#dependency-resolution-in-nuget-3-x) auf der NuGet-Dokumentationswebsite.

Zum Beispiel:

```json
    "dependencies": {
        "System.Reflection.Metadata": "1.3.0",
        "Microsoft.Extensions.JsonParser.Sources": {
          "type": "build",
          "version": "1.0.0-rc2-20221"
        },
        "Microsoft.Extensions.HashCodeCombiner.Sources": {
          "type": "build",
          "version": "1.1.0-alpha1-21456"
        },
        "Microsoft.Extensions.DependencyModel": "1.0.0-*"
    }
```

### <a name="version"></a>Version
Typ: Zeichenfolge

Gibt die Version oder den Versionsbereich der Abhängigkeit an. Verwenden des Platzhalters \*, um eine [floating dependency version](https://docs.nuget.org/ndocs/consume-packages/dependency-resolution#floating-versions) (unverankerte Abhängigkeitsversion) zu definieren.

Zum Beispiel:

```json
"dependencies": { 
    "Newtonsoft.Json": { 
        "version": "9.0.1" 
    }
}
```

### <a name="type"></a>Typ
Typ: Zeichenfolge

Gibt den Typ der Abhängigkeit an. Kann einer der folgenden Werte sein: `default`, `build` oder `platform`. Der Standardwert ist `default`.

`build` wird als Abhängigkeitsentwicklung bezeichnet und nur für die Buildzeit verwendet. Das bedeutet, dass das Paket nicht veröffentlicht oder als Abhängigkeit zur Ausgabedatei `.nupkg` hinzugefügt werden sollte. Es hat die gleiche Auswirkung wie das Festlegen von [supressParent](#supressparent) auf `all`.

`platform` verweist auf das freigegebene SDK. Weitere Informationen finden Sie im Abschnitt „Deploying a framework-dependent deployment with third-party dependencies (Bereitstellen einer Framework-abhängigen Bereitstellung mit Drittanbieter-Abhängigkeiten)“ im Thema [.NET Core Application Deployment (.NET Core-Anwendungsbereitstellung)](../deploying/index.md).

Beispiel:

```json
 "dependencies": {
   "Microsoft.NETCore.App": {
     "type": "platform",
     "version": "1.0.0"
   }
 }
```

### <a name="target"></a>target
Typ: Zeichenfolge

Schränkt die Abhängigkeit ein, nur mit `project` oder `package` übereinzustimmen.

### <a name="include"></a>include
Typ: Zeichenfolge

Enthält Teile der Abhängigkeitspakete. Eine oder mehrere der folgenden Flags können verwendet werden: `all`, `runtime`, `compile`, `build`, `contentFiles`, `native`, `analyzers` oder `none`.
Mehrere Flags werden durch eine durch Komma getrennte Liste definiert.
Weitere Informationen finden Sie unter der Spezifikation [Managing dependency package asset (Verwalten von Objekten von Abhängigkeitspaketen)](https://github.com/NuGet/Home/wiki/%5BSpec%5D-Managing-dependency-package-assets) im NuGet-Repository.

Zum Beispiel:

```json
{
  "dependencies": {
    "packageA": {
      "version": "1.0.0",
      "include": "runtime"
    }
  }
}
```

### <a name="exclude"></a>exclude
Typ: Zeichenfolge

Schließt Teile der Abhängigkeitspakete aus. Eine oder mehrere der folgenden Flags können verwendet werden: `all`, `runtime`, `compile`, `build`, `contentFiles`, `native`, `analyzers` oder `none`.
Mehrere Flags werden durch eine durch Komma getrennte Liste definiert.
Weitere Informationen finden Sie unter der Spezifikation [Managing dependency package asset (Verwalten von Objekten von Abhängigkeitspaketen)](https://github.com/NuGet/Home/wiki/%5BSpec%5D-Managing-dependency-package-assets) im NuGet-Repository.

Zum Beispiel:

```json
{
  "dependencies": {
    "packageA": {
      "version": "1.0.0",
      "exclude": "contentFiles"
    }
  }
}
```

### <a name="supressparent"></a>supressParent
Typ: Zeichenfolge

Definiert zusätzliche Ausschlüsse für Consumer des Projekts. Eine oder mehrere der folgenden Flags können verwendet werden: `all`, `runtime`, `compile`, `build`, `contentFiles`, `native`, `analyzers` oder `none`.
Weitere Informationen finden Sie unter der Spezifikation [Managing dependency package asset (Verwalten von Objekten von Abhängigkeitspaketen)](https://github.com/NuGet/Home/wiki/%5BSpec%5D-Managing-dependency-package-assets) im NuGet-Repository.

```json
{
  "dependencies": {
    "packageA": {
      "version": "1.0.0",
      "suppressParent": "compile"
    }
  }
}
```

## <a name="tools"></a>Tools
Typ: Objekt

Ein Objekt, das Paketabhängigkeiten definiert, die als Tools für das aktuelle Projekt verwendet werden, nicht als Verweise. Pakete, die hier definiert werden, sind in Skripts verfügbar, die während des Buildprozesses ausgeführt werden, aber nicht auf den Code im Projekt selbst zugreifen können. Tools können z.B. Codegeneratoren oder Postbuild-Tools umfassen, die Aufgaben im Zusammenhang mit dem Verpacken ausführen.

Zum Beispiel:

```json
{
    "tools": {
    "MyObfuscator": "1.2.4"
    }
}
```

## <a name="scripts"></a>Skripts
Typ: Objekt

Ein Objekt, das Skripts definiert, die während des Buildprozesses ausgeführt werden. Jeder Schlüssel in diesem Objekt identifiziert, wo im Build das Skript ausgeführt wird. Jeder Wert ist entweder eine Zeichenfolge mit dem auszuführenden Skript oder ein Array von Zeichenfolgen, das Skripts enthält, die der Reihe nach ausgeführt werden.
Die unterstützten Ereignisse sind:
* precompile
* postcompile
* prepublish
* postpublish

Zum Beispiel:

```json
{
    "scripts": {
        "precompile": "generateCode.cmd",
        "postcompile": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
    }
}
```

## <a name="buildoptions"></a>buildOptions
Typ: Objekt

Ein Objekt, dessen Eigenschaften verschiedene Aspekte der Kompilierung steuern. Die gültigen Eigenschaften sind unten aufgelistet. Kann auch pro Zielframework angegeben werden, wie im Abschnitt [Frameworks](#frameworks) beschrieben.

Zum Beispiel:

```json
    "buildOptions": {
      "allowUnsafe": true,
      "emitEntryPoint": true
    }
```

### <a name="define"></a>define
Typ: Zeichenfolge[]

Eine Liste von Defines wie „DEBUG“ oder „TRACE“, die in der bedingten Kompilierung im Code verwendet werden können.

Zum Beispiel:

```json
{
    "buildOptions": {
        "define": ["TEST", "OTHERCONDITION"]
    }
}
```

### <a name="nowarn"></a>nowarn
Typ: Zeichenfolge[]

Eine Liste von Warnungen, die ignoriert werden können.

Zum Beispiel:

```json
{
    "buildOptions": {
        "nowarn": ["CS0168", "CS0219"]
    }
}
```

Dies ignoriert die Warnungen `The variable 'var' is declared but never used` und `The variable 'var' is assigned but its value is never used`.

### <a name="additionalarguments"></a>additionalArguments
Typ: Zeichenfolge[]

Eine Liste mit zusätzlichen Argumenten, die an den Compiler übergeben werden.

Zum Beispiel:

```json
{
    "buildOptions": {
        "additionalArguments": ["/parallel", "/nostdlib"]
    }
}
```

### <a name="warningsaserrors"></a>warningsAsErrors
Typ: Boolesch

`true` zum Behandeln aller Warnungen als Fehler, andernfalls `false`. Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "buildOptions": {
        "warningsAsErrors": true
    }
}
```

### <a name="allowunsafe"></a>allowUnsafe
Typ: Boolesch

`true` zum Erlauben von unsicherem Code in diesem Projekt, andernfalls `false`. Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "buildOptions": {
        "allowUnsafe": true
    }
}
```

### <a name="emitentrypoint"></a>emitEntryPoint
Typ: Boolesch

`true`zum Erstellen einer ausführbaren Datei. `false` zum Erstellen einer Bibliothek. Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "buildOptions": {
        "emitEntryPoint": true
    }
}
```

### <a name="optimize"></a>optimize
Typ: Boolesch

`true` zum Aktivieren des Compilers, um den Code in diesem Projekt zu optimieren, andernfalls `false`. Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "buildOptions": {
        "optimize": true
    }
}
```

### <a name="platform"></a>platform
Typ: Zeichenfolge

Der Name der Zielplattform, z.B. AnyCpu, x86 oder x64.

Zum Beispiel:

```json
{
    "buildOptions": {
        "platform": "x64"
    }
}
```

### <a name="languageversion"></a>languageVersion
Typ: Zeichenfolge

Die Version der vom Compiler verwendeten Sprache: ISO-1, ISO-2, 3, 4, 5, 6 oder Standard.

Zum Beispiel:

```json
{
    "buildOptions": {
        "languageVersion": "5"
    }
}
```

### <a name="keyfile"></a>keyFile
Typ: Zeichenfolge

Der Pfad für die Schlüsseldatei zum Signieren der Assembly.

Zum Beispiel:

```json
{
    "buildOptions": {
        "keyFile": "../keyfile.snk"
    }
}
```

### <a name="delaysign"></a>delaySign
Typ: Boolesch

`true` zur Verzögerung des Signierens, andernfalls `false`. Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "buildOptions": {
        "delaySign": true
    }
}
```

### <a name="publicsign"></a>publicSign
Typ: Boolesch

`true` zum Aktivieren des Signierens der resultierenden Assembly, andernfalls `false`. Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "buildOptions": {
        "publicSign": true
    }
}
```

### <a name="debugtype"></a>debugType
Typ: Zeichenfolge

Gibt den Typ der zu generierenden Symboldatei (PDB-Datei) an. Die Optionen sind „portabel“ (für .NET Core-Projekte) oder „voll“ (die herkömmlichen PDB-Dateien nur für Windows).

Zum Beispiel:

```json
{
    "buildOptions": {
        "debugType": "portable"
    }
}
```

### <a name="xmldoc"></a>xmlDoc
Typ: Boolesch

`true` zum Generieren von XML-Dokumentation aus Kommentaren mit drei Schrägstrichen im Quellcode, andernfalls `false`. Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "buildOptions": {
        "xmlDoc": true
    }
}
```

### <a name="preservecompilationcontext"></a>preserveCompilationContext
Typ: Boolesch

`true` zum Beibehalten von Verweisassemblys und anderen Kontextdaten zur Laufzeitkompilierung, andernfalls `false`. Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "buildOptions": {
        "preserveCompilationContext": true
    }
}
```

### <a name="outputname"></a>outputName
Typ: Zeichenfolge

Ändern des Namens der Ausgabedatei. 

Zum Beispiel:

```json
{
    "buildOptions": {
        "outputName": "MyApp"
    }
}
```

### <a name="compilername"></a>compilerName
Typ: Zeichenfolge

Der Name des Compilers, der für dieses Projekt verwendet wird. `csc` standardmäßig. Derzeit wird `csc` (der C#-Compiler) oder `fsc` (der F#-Compiler) unterstützt.
 
Zum Beispiel:

```json
{
    "compilerName": "fsc"
}
```
    
### <a name="compile"></a>compile
Typ: Objekt

Ein Objekt, das Eigenschaften für die Konfiguration der Kompilierung enthält.

#### <a name="include"></a>include
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

Gibt an, welche Dateien im Build enthalten sein sollen. Die Muster haben den Projektordner als Stamm. Der Standardwert ist „None“.

Zum Beispiel:

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

Gibt an, welche Dateien vom Build ausgeschlossen werden. Die Muster in „exclude“ haben höhere Priorität als die Muster in „include“, deswegen wird eine Datei ausgeschlossen, die in beiden gefunden wird. Die Muster haben den Projektordner als Stamm. Der Standardwert ist „None“.

Zum Beispiel:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

Eine Liste der Dateipfade, die aufgenommen werden sollen. Die Pfade haben den Projektordner als Stamm. Diese Liste hat eine höhere Priorität als die Platzhaltermuster „include“ und „exclude“, daher wird eine Datei trotzdem eingeschlossen, die hier und im Platzhaltermuster „exclude“ aufgelistet ist. Der Standardwert ist „None“.

Zum Beispiel:

```json
{
    "includeFiles": []
}
```

#### <a name="excludefiles"></a>excludeFiles

Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

Eine Liste der Dateipfade, die ausgeschlossen werden sollen. Die Pfade haben den Projektordner als Stamm. Diese Liste hat eine höhere Priorität als Platzhaltermuster und umfasst Pfade, daher wird eine Datei ausgeschlossen, die in allen gefunden wird. Der Standardwert ist „None“.

Zum Beispiel:

```json
{
    "excludeFiles":[],
}
```

#### <a name="builtins"></a>builtIns

Typ: Objekt

Die Standardwerte, die vom System bereitgestellt werden. Kann Platzhaltermuster `include` und `exclude` enthalten, die mit den entsprechenden Werten der Eigenschaften `include` und `exclude` zusammengeführt werden.

Zum Beispiel:

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>Zuordnungen
Typ: Objekt

Schlüssel zum Objekt stellen Zielpfade im Ausgabelayout dar.

Werte sind entweder eine Zeichenfolge oder ein Objekt, das den Quellpfad der einzuschließenden Dateien darstellt.  Die Objektdarstellung kann über eigene Abschnitte `include`, `exclude`, `includeFiles` und `excludeFiles` verfügen.

Beispiel für Zeichenfolge:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Beispiel für Objekt:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

### <a name="embed"></a>embed
Typ: Objekt

Ein Objekt, das Eigenschaften für die Konfiguration der Kompilierung enthält.

#### <a name="include"></a>include
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

Gibt an, welche Dateien vom Build ausgeschlossen werden.

Zum Beispiel:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "includeFiles":[],
}
```

#### <a name="excludefiles"></a>excludeFiles

Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "excludeFiles":[],
}
```

#### <a name="builtins"></a>builtIns
Typ: Objekt

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>Zuordnungen
Typ: Objekt

Schlüssel zum Objekt stellen Zielpfade im Ausgabelayout dar.

Werte sind entweder eine Zeichenfolge oder ein Objekt, das den Quellpfad der einzuschließenden Dateien darstellt.  Die Objektdarstellung kann über eigene Abschnitte `include`, `exclude`, `includeFiles` und `excludeFiles` verfügen.

Beispiel für Zeichenfolge:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Beispiel für Objekt:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

### <a name="copytooutput"></a>copyToOutput
Typ: Objekt

Ein Objekt, das Eigenschaften für die Konfiguration der Kompilierung enthält.

#### <a name="include"></a>include
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

Gibt an, welche Dateien vom Build ausgeschlossen werden.

Zum Beispiel:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "includeFiles":[],
}
```

#### <a name="excludefiles"></a>excludeFiles

Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "excludeFiles":[],
}
```

#### <a name="builtins"></a>builtIns
Typ: Objekt

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>Zuordnungen
Typ: Objekt

Schlüssel zum Objekt stellen Zielpfade im Ausgabelayout dar.

Werte sind entweder eine Zeichenfolge oder ein Objekt, das den Quellpfad der einzuschließenden Dateien darstellt.  Die Objektdarstellung kann über eigene Abschnitte `include`, `exclude`, `includeFiles` und `excludeFiles` verfügen.

Beispiel für Zeichenfolge:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Beispiel für Objekt:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

## <a name="publishoptions"></a>publishOptions
Typ: Objekt

Ein Objekt, das Eigenschaften für die Konfiguration der Kompilierung enthält.

### <a name="include"></a>include
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "include":["wwwroot", "Views"]
}
```

### <a name="exclude"></a>exclude
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

Gibt an, welche Dateien vom Build ausgeschlossen werden.

Zum Beispiel:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

### <a name="includefiles"></a>includeFiles

Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "includeFiles":[],
}
```

### <a name="excludefiles"></a>excludeFiles

Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "excludeFiles":[],
}
```

### <a name="builtins"></a>builtIns
Typ: Objekt

```json
{
    "builtIns":{}
}
```

### <a name="mappings"></a>Zuordnungen
Typ: Objekt

Schlüssel zum Objekt stellen Zielpfade im Ausgabelayout dar.

Werte sind entweder eine Zeichenfolge oder ein Objekt, das den Quellpfad der einzuschließenden Dateien darstellt.  Die Objektdarstellung kann über eigene Abschnitte `include`, `exclude`, `includeFiles` und `excludeFiles` verfügen.

Beispiel für Zeichenfolge:

```json
{
    "mappings": {
        "dest/file": "./src/file",
        "dest/folder/": "./src/folder/**/*"
    }
}
```

Beispiel für Objekt:

```json
{
    "mappings": {
        "dest/file":{
            "include":"./src/file"
        },
        "dest/folder/":{
            "include":"./src/folder/**/*"
        }
    }
}
```

## <a name="runtimeoptions"></a>runtimeOptions
Typ: Objekt

Gibt Parameter für die Laufzeit während der Initialisierung an.

### <a name="configproperties"></a>configProperties
Typ: Objekt

Enthält Eigenschaften zum Konfigurieren der Laufzeit und des Frameworks.

#### <a name="systemgcserver"></a>System.GC.Server
Typ: Boolesch

`true` zum Aktivieren der Garbage Collection für Server, andernfalls `false`. Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.GC.Server": true
        }
    }
}
```

#### <a name="systemgcconcurrent"></a>System.GC.Concurrent
Typ: Boolesch

`true` zum Aktivieren von gleichzeitigen Garbage Collection-Vorgängen, andernfalls `false`. Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.GC.Concurrent": true
        }
    }
}
```

#### <a name="systemgcretainvm"></a>System.GC.RetainVM
Typ: Boolesch

`true` zum Platzieren von zu löschenden Segmenten auf einer Standby-Liste für die zukünftige Verwendung statt erneuter Freigabe an das Betriebssystem (OS), andernfalls `false`.
Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.GC.RetainVM": true
        }
    }
}
```

#### <a name="systemthreadingthreadpoolminthreads"></a>System.Threading.ThreadPool.MinThreads
Typ: Ganze Zahl

Überschreibt die Mindestanzahl von Threads für den Arbeitspool von ThreadPool.

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.Threading.ThreadPool.MinThreads": 4
        }
    }
}
```

#### <a name="systemthreadingthreadpoolmaxthreads"></a>System.Threading.ThreadPool.MaxThreads
Typ: Ganze Zahl

Überschreibt die Höchstanzahl von Threads für den Arbeitspool von ThreadPool.

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.Threading.ThreadPool.MaxThreads": 25
        }
    }
}
```

### <a name="framework"></a>Framework
Typ: Objekt

Enthält freigegebene Frameworkeigenschaften, die beim Aktivieren der Anwendung verwendet werden sollen. Wenn dieser Bereich vorhanden ist bedeutet das, dass die Anwendung eine portable App ist, die für die Verwendung von freigegebenen verteilbaren Frameworks konzipiert ist.

#### <a name="name"></a>Name
Typ: Zeichenfolge

Name des freigegebenen Frameworks.

```json
{
    "runtimeOptions": {
        "framework": {
            "name": "Microsoft.DotNetCore"
        }
    }
}
```

#### <a name="version"></a>Version
Typ: Zeichenfolge

Version des freigegebenen Frameworks.

```json
{
    "runtimeOptions": {
        "framework": {
            "version": "1.0.1"
        }
    }
}
```

### <a name="applypatches"></a>applyPatches
Typ: Boolesch

`true` zum Verwenden des Frameworks über die gleiche oder eine höhere Version, die sich nur im Patchfeld `SemVer` unterscheidet. `false` als Angabe für den Host, ausschließlich die genaue Version des Frameworks zu verwenden. Die Standardeinstellung ist `true`.

```json
{
    "runtimeOptions": {
        "applyPatches": false
    }
}
```

## <a name="packoptions"></a>packOptions
Typ: Objekt

Definiert Optionen, die das Verpacken der Projektausgabe in ein NuGet-Paket betreffen.

### <a name="summary"></a>Zusammenfassung
Typ: Zeichenfolge

Eine kurze Beschreibung des Projekts.

Zum Beispiel:

```json
{
    "packOptions": {
        "summary": "This is my library."
    }
}
```

### <a name="tags"></a>Tags
Typ: Zeichenfolge[]

Ein Array von Zeichenfolgen mit Tags für das Projekt, die für die Suche in NuGet verwendet werden.

Zum Beispiel:

```json
{
    "packOptions": {
        "tags": ["hyperscale", "cats"]
    }
}
```

### <a name="owners"></a>owners
Typ: Zeichenfolge[]

Ein Array von Zeichenfolgen mit den Namen der Besitzer des Projekts.

Zum Beispiel:

```json
{
    "packOptions": {
        "owners": ["Fabrikam", "Microsoft"]
    }
}
```

### <a name="releasenotes"></a>releaseNotes
Typ: Zeichenfolge

Anmerkungen zu diesem Projekt.

Zum Beispiel:

```json
{
    "packOptions": {
        "releaseNotes": "Initial version, implemented flimflams."
    }
}
```

### <a name="iconurl"></a>iconUrl
Typ: Zeichenfolge

Die URL für ein Symbol, das in verschiedenen Orten wie z.B. im Paket-Explorer verwendet wird.

Zum Beispiel:

```json
{
    "packOptions": {
        "iconUrl": "http://www.mylibrary.gov/favicon.ico"
    }
}
```

### <a name="projecturl"></a>projectUrl
Typ: Zeichenfolge

Die URL für die Startseite des Projekts.

Zum Beispiel:

```json
{
    "packOptions": {
        "projectUrl": "http://www.mylibrary.gov"
    }
}
```

### <a name="licenseurl"></a>licenseUrl
Typ: Zeichenfolge

Die URL für die Lizenz, die das Projekt verwendet.

Zum Beispiel:

```json
{
    "packOptions": {
        "licenseUrl": "http://www.mylibrary.gov/licence"
    }
}
```

### <a name="requirelicenseacceptance"></a>requireLicenseAcceptance
Typ: Boolesch

`true` zum Verursachen einer Eingabeaufforderung, um die Lizenz des Pakets zu akzeptieren, wenn das Paket, das angezeigt werden soll, installiert wird, andernfalls `false`. Nur für NuGet-Pakete, bei anderen Verwendungen ignoriert. Die Standardeinstellung ist `false`.

Zum Beispiel:

```json
{
    "packOptions": {
        "requireLicenseAcceptance": true
    }
}
```
   
### <a name="repository"></a>Repository
Typ: Objekt

Enthält Informationen über das Repository, in dem das Projekt gespeichert ist.

#### <a name="type"></a>Typ
Typ: Zeichenfolge

Der Typ des Repositorys. Der Standardwert ist „git“.

Zum Beispiel:

```json
{
    "packOptions": {
        "repository": {
            "type": "git"
        }
    }
}
```

#### <a name="url"></a>url
Typ: Zeichenfolge

URL des Repositorys, in dem das Projekt gespeichert ist.

Zum Beispiel:

```json
{
    "packOptions": {
        "repository": {
            "url": "http://github.com/dotnet/corefx"
        }
    }
}
```

### <a name="files"></a>Dateien
Typ: Objekt

#### <a name="include"></a>include
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

Gibt an, welche Dateien vom Build ausgeschlossen werden.

Zum Beispiel:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "includeFiles":[]
}
```

#### <a name="excludefiles"></a>excludeFiles

Typ: Zeichenfolge oder Zeichenfolge[] mit einem Platzhaltermuster.

```json
{
    "excludeFiles":[]
}
```

#### <a name="builtins"></a>builtIns
Typ: Objekt

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>Zuordnungen
Typ: Objekt

Schlüssel zum Objekt stellen Zielpfade im Ausgabelayout dar.

Werte sind entweder eine Zeichenfolge oder ein Objekt, das den Quellpfad der einzuschließenden Dateien darstellt.  Die Objektdarstellung kann über eigene Abschnitte `include`, `exclude`, `includeFiles` und `excludeFiles` verfügen. 

Beispiel für Zeichenfolge:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Beispiel für Objekt:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

## <a name="analyzeroptions"></a>analyzerOptions
Typ: Objekt

Ein Objekt mit Eigenschaften, die bei der Analyse von Code verwendet werden.

Zum Beispiel:

```json
{
    "analyzerOptions": { }
}
```

### <a name="languageid"></a>languageId
Typ: Zeichenfolge

Die ID der zu analysierenden Sprache. „cs“ steht für C#, „vb“ steht für Visual Basic und „fs“ steht für F#.

Zum Beispiel:

```json
"analyzerOptions": {
    "languageId": "vb"
}
```

## <a name="configurations"></a>Konfigurationen
Typ: Objekt

Ein Objekt, dessen Eigenschaften verschiedene Konfigurationen für dieses Projekt angeben, wie Debug und Release. Jeder Wert ist ein Objekt, das ein `buildOptions`-Objekt mit für diese Konfiguration spezifischen Optionen enthalten kann.

Zum Beispiel:

```json
"configurations": {
    "Release": {
        "buildOptions": {
            "allowUnsafe": false
        }
    }
}
```

## <a name="frameworks"></a>frameworks
Typ: Objekt

Gibt an, welche Frameworks dieses Projekt unterstützt, z.B. .NET Framework oder Universelle Windows-Plattform (UWP). Es muss ein gültiger Zielframeworkmoniker (Target Framework Moniker, TMF) sein. Jeder Wert ist ein Objekt, das Informationen zu diesem Framework enthalten kann, z.B. `buildOptions`, `analyzerOptions`, `dependencies`, sowie die Eigenschaften in den folgenden Abschnitten.

Zum Beispiel:

```json
"frameworks": {
    "netcoreapp1.0": {
        "buildOptions": {
            "define": ["FOO", "BIZ"]
        }
    }
}
```

### <a name="dependencies"></a>Abhängigkeiten
Typ: Objekt

Abhängigkeiten, die für dieses Framework spezifisch sind. Dies ist in Szenarios nützlich, in denen Sie nicht einfach eine Abhängigkeit auf Paketebene auf allen Zielen angeben können. Ursachen hierfür können sein, dass einem Ziel die integrierte Unterstützung fehlt, die andere Ziele haben, oder dass eine andere Version einer Abhängigkeit benötigt wird als bei anderen Zielen. Eine Liste der anderen Eigenschaften für diesen Knoten finden Sie im obigen Abschnitt [dependencies](#dependencies).

Zum Beispiel:

```json
    "frameworks": {
        "netstandard1.5": {
        "dependencies": {
            "Microsoft.Extensions.JsonParser.Sources": "1.0.0-rc2-20221"
        }
    }
}
```

### <a name="frameworkassemblies"></a>frameworkAssemblies
Typ: Objekt

Ähnlich wie Abhängigkeiten, enthält jedoch Verweise auf Assemblys im GAC, die keine NuGet-Pakete sind. Kann auch die zu verwendende Version sowie den Typ der Abhängigkeit angeben. Wird benutzt, wenn Ziele von .NET Frameworks und Portable Klassenbibliothek (PCL) als Ziel gesetzt werden. Sie können ein Projekt mit dieser Angabe nur auf Windows erstellen.

Zum Beispiel:

```json
"frameworks": {
    "net451": {
        "frameworkAssemblies": {
            "System.Runtime": {
                "type": "build",
                "version": "4.0.0"
            }
        }
    }
}
```

### <a name="wrappedproject"></a>wrappedProject
Typ: Zeichenfolge

Gibt den Speicherort des Abhängigkeitsprojekts an. 

Zum Beispiel:

```json
"frameworks": {
    "net451": {
        "wrappedProject": "MyProject.csproj"
    }
}
```

### <a name="bin"></a>bin
Typ: Objekt

Wird verwendet, um eine DLL-Datei zu umschließen. Sie können auf ein Paket, das diese DLL enthält, verweisen und es erzeugen. 

Es enthält eine Eigenschaft einer einzelnen Zeichenfolge, `assembly`, deren Wert der Assemblypfad ist.   

Zum Beispiel:

```json
"frameworks": {
    "netcoreapp1.0": {
        "bin": {
            "assembly": "c:/otherProject/otherdll.dll"
        }
    }
}
```

## <a name="runtimes"></a>Laufzeiten
Typ: Objekt

Liste der [Runtime-IDs (RIDs)](../rid-catalog.md), die vom Projekt (bei der Veröffentlichung von [self-contained deployments (eigenständigen Bereitstellungen)](../deploying/index.md#self-contained-deployments-scd)) unterstützt werden.

Zum Beispiel:

```json
"runtimes": {
    "win7-x64": {},
    "win8-x64": {},
    "win81-x64": {},
    "win10-x64": {},
    "osx.10.11-x64": {},
    "ubuntu.16.04-x64": {}
}
```

## <a name="usersecretsid"></a>userSecretsId
Typ: Zeichenfolge

Gibt eine geheime Benutzer-ID an, die zum Zeitpunkt der Entwicklung verwendet wird. Weitere Informationen finden Sie im Dokument [Safe storage of app secrets during development (Sicheres Speichern geheimer App-Daten während der Entwicklung)](https://docs.asp.net/en/latest/security/app-secrets.html).

Zum Beispiel:

```json
{
    "userSecretsId": "aspnet-WebApp1-c23d27a4-eb88-4b18-9b77-2a93f3b15119"
}
```



<!--HONumber=Jan17_HO3-->


