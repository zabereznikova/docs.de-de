---
title: 'Vorgehensweise: Installieren einer Assembly im globalen Assemblycache'
ms.date: 02/05/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 233a7803cb59f9bfeac15d293dc3fb5a0db449c9
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903764"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Vorgehensweise: Installieren einer Assembly im globalen Assemblycache

Im globalen Assemblycache (GAC) werden Assemblys gespeichert, die von mehreren Anwendungen gemeinsam verwendet werden. Installieren Sie eine Assembly mit einer der folgenden Komponenten in den [globalen Assemblycache](gac.md): 
- [Windows Installer](#windows-installer)
- [Globaler Assemblycache (Tool)](#global-assembly-cache-tool)

> [!IMPORTANT]
> Sie können nur Assemblys mit starkem Namen können im GAC installieren. Informationen zum Erstellen von Assemblys mit starkem Namen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](how-to-sign-an-assembly-with-a-strong-name.md).

## <a name="windows-installer"></a>Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), das Windows-Installationsmodul, stellt das empfohlene Verfahren zum Hinzufügen von Assemblys zum globalen Assemblycache dar. Der Windows Installer bietet neben einem Verweiszähler für Assemblys im globalen Assemblycache noch weitere Vorteile. Verwenden Sie die [WiX-Toolseterweiterung für Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension), um ein Installationspaket für Windows Installer zu erstellen.

## <a name="global-assembly-cache-tool"></a>Globaler Assemblycache-Tool

Mit dem [Tool für den globalen Assemblycache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) können Sie Assemblys zum globalen Assemblycache hinzufügen und sich dessen Inhalt anzeigen lassen.

   > [!NOTE]
   > Die *gacutil.exe* ist nur für Entwicklungszwecke vorgesehen. Verwenden Sie die ausführbare Datei nicht zum Installieren von Produktionsassemblys in den globalen Assemblycache.

Die Syntax zur Verwendung der *gacutil.exe* zum Installieren einer Assembly im GAC lautet wie folgt:

```console
gacutil -i <assembly name>
```

In diesem Befehl bezeichnet *\<Assemblyname>* den Namen der Assembly, die im globalen Assemblycache installiert werden soll.

Wenn die *gacutil.exe* sich nicht in Ihrem Systempfad befindet, verwenden Sie die [Developer-Eingabeaufforderung für VS *\<Version>*](../tools/developer-command-prompt-for-vs.md).

Im folgenden Beispiel wird eine Assembly mit dem Dateinamen *hello.dll* im globalen Assemblycache installiert.

```console
gacutil -i hello.dll
```

> [!NOTE]
> In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung *Shfusion.dll* das Installieren von Assemblys durch Verschieben in den Datei-Explorer. Die *Shfusion.dll* ist seit .NET Framework 4 veraltet.

## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Assemblys und dem globalen Assemblychache](working-with-assemblies-and-the-gac.md)
- [Vorgehensweise: Entfernen einer Assembly aus dem globalen Assemblycache](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (Global assembly cache tool) (Gacutil.exe (Tool für den globalen Assemblycache))](../tools/gacutil-exe-gac-tool.md)
- [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](how-to-sign-an-assembly-with-a-strong-name.md)
