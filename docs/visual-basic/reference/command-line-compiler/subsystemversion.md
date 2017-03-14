---
title: "-Subsystemversion (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
helpviewer_keywords: 
  - "/subsystemversion-Compileroption [Visual Basic]"
  - "-subsystemversion-Compileroption [Visual Basic]"
  - "subsystemversion-Compileroption [Visual Basic]"
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# /subsystemversion (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt die Mindestversion des Subsystems, auf dem die generierte ausführbare Datei ausführen kann, und bestimmen die Versionen von Windows auf dem die ausführbare Datei ausgeführt werden kann. In den meisten Fällen wird diese Option sichergestellt, die ausführbare Datei bestimmte Sicherheitsfunktionen nutzen, die nicht mit älteren Versionen von Windows verfügbar sind.  
  
> [!NOTE]
>  Verwenden Sie zum Angeben der Subsystem selbst die [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) (Compileroption).  
  
## <a name="syntax"></a>Syntax  
  
```vb  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a>Parameter  
 `major.minor`  
 Die mindestens erforderliche Version des Subsystems, ausgedrückt in eine punktierte Schreibweise für Haupt-und Nebenversionen. Beispielsweise können Sie angeben, dass eine Anwendung unter einem Betriebssystem werden, die älter als Windows 7 ausgeführt kann wenn 6.01, den Wert dieser Option fest, wie in der Tabelle weiter unten in diesem Thema beschrieben. Geben Sie die Werte für `major` und `minor` als ganze Zahlen.  
  
 Führende Nullen in der `minor` Version nicht die Version geändert, aber nachfolgende Nullen werden. Z. B. 6.1 und 6.01 beziehen sich auf die gleiche Version, aber 6.10 bezieht sich auf eine andere Version. Es wird empfohlen, die Nebenversion auszudrücken, als zwei Ziffern, um Verwechslungen zu vermeiden.  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält allgemeine Subsystemversionen von Windows.  
  
|Windows-Version|Subsystem-version|  
|---------------------|-----------------------|  
|Windows 2000|5.00|  
|Windows XP|5.01|  
|Windows Server 2003|5.02|  
|Windows Vista|6.00|  
|Windows 7|6.01|  
|Windows Server 2008|6.01|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|6.02|  
  
## <a name="default-values"></a>Standardwerte  
 Der Standardwert der **/subsystemversion** (Compileroption) hängt von der Bedingung in der folgenden Liste:  
  
-   Der Standardwert ist 6.02, wenn jede Compileroption in der folgenden Liste festgelegt wird:  
  
    -   [/ target: appcontainerexe](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [/ target: winmdobj](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [/Platform:ARM](../../../visual-basic/reference/command-line-compiler/platform.md)  
  
-   Der Standardwert ist 6.00, wenn Sie MSBuild verwenden, die Sie als Ziel [!INCLUDE[net_v45](~/includes/net-v45-md.md)], und Sie können alle Compileroptionen, die zuvor in dieser Liste angegeben wurden noch nicht festlegen.  
  
-   Der Standardwert ist 4.00, wenn keine der vorherigen Bedingungen true ist.  
  
## <a name="setting-this-option"></a>Festlegen dieser Option  
 Festlegen der **/subsystemversion** -Compileroption in Visual Studio müssen Sie öffnen die VBPROJ-Datei und geben Sie einen Wert für die `SubsystemVersion` Eigenschaft in der MSBuild-XML. Diese Option kann nicht in der Visual Studio-IDE festgelegt werden. Weitere Informationen finden Sie unter "Standardwerte" weiter oben in diesem Thema oder [gemeinsame MSBuild-Projekteigenschaften](/visual-studio/msbuild/common-msbuild-project-properties).  
  

  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
 [MSBuild-Eigenschaften](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/ee3538c5-0d7d-4c18-a1d7-edf460cd1c8a/locales/en-US)