---
title: 'Vorgehensweise: ermitteln, welche .NET Framework-Sicherheit-Updates und Hotfixes installiert sind'
description: Informationen Sie zum bestimmen, welche .NET Framework-Sicherheit-Updates und Hotfixes auf einem Computer installiert sind.
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c35705470a8e1b553eca2ca0c68d3b8b9b3f6fa6
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>Vorgehensweise: ermitteln, welche .NET Framework-Sicherheit-Updates und Hotfixes installiert sind

Diesem Artikel erfahren Sie, wie Sie herausfinden, welche .NET Framework-Sicherheitsupdates und Hotfixes auf einem Computer installiert sind.

> [!NOTE]
> Die Techniken, die in diesem Artikel angezeigten erfordern ein Konto mit Administratorrechten aus.

## <a name="to-find-installed-updates-using-the-registry"></a>Suchen Sie installierte Updates mithilfe der Registrierung

Die installierten Sicherheitsupdates und Hotfixes für jede Version von .NET Framework auf einem Computer installiert sind, werden in der Windows-Registrierung aufgeführt. Sie können den Registrierungs-Editor (*regedit.exe*) Programm zum Anzeigen dieser Informationen.

1. Öffnen Sie das Programm **regedit.exe**. In Windows 8 und höher, mit der Maustaste **starten** ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), und wählen Sie dann **ausführen**. In der **öffnen** geben **Regedit** , und wählen Sie **OK**.

2. Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     Die installierten Updates werden unter Unterschlüsseln aufgeführt, die die für sie geltende .NET Framework-Version identifizieren. Jedes Update wird durch eine Knowledge Base (KB)-Nummer identifiziert.

Im Registrierungs-Editor werden die .NET Framework-Versionen und die installierten Updates für jede Version in verschiedenen Unterschlüsseln gespeichert. Informationen zum Ermitteln der installierten Versionsnummern finden Sie unter [wie: bestimmen, welche .NET Framework-Versionen installiert sind](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a>Um installierten Updates durch Abfragen der Registrierungs im code

Im folgende Beispiel ermittelt programmgesteuert die .NET Framework-Sicherheitsupdates und Hotfixes, die auf einem Computer installiert sind:

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

Das Beispiel führt eine Ausgabe, die mit dem folgenden ähnlich ist:

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a>Um installierten Updates durch Abfragen der Registrierungs in PowerShell

Das folgende Beispiel zeigt, wie bestimmt wird, die .NET Framework-Sicherheitsupdates und Hotfixes, die mithilfe von PowerShell auf einem Computer installiert sind:

```powershell
 Get-ChildItem "HKLM:SOFTWARE\Wow6432Node\Microsoft\Updates\*" -Recurse | Where-Object {$_.name -like
 "*.NET Framework*"}
```

Das Beispiel führt eine Ausgabe, die mit dem folgenden ähnlich ist:

```console
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Client Profile


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y


    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Extended


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y
```

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: bestimmen, welche .NET Framework-Versionen installiert sind](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[Installieren Sie .NET Framework für Entwickler](../../../docs/framework/install/guide-for-developers.md)  
[Versionen und-Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md)
