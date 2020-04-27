---
title: Ausführen von Intranetanwendungen mit voller Vertrauenswürdigkeit
ms.date: 03/30/2017
helpviewer_keywords:
- full trust, running intranet applications in
- intranet applications, running in full trust
- running intranet applications in full trust
ms.assetid: ee13c0a8-ab02-49f7-b8fb-9eab16c6c4f0
ms.openlocfilehash: 33b025fa62343277fc96fc7771587e95f556e7a6
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645449"
---
# <a name="running-intranet-applications-in-full-trust"></a>Ausführen von Intranetanwendungen mit voller Vertrauenswürdigkeit

Ab .NET Framework version 3.5 Service Pack 1 (SP1) können Anwendungen und deren Bibliothekassemblys als Assemblys mit voller Vertrauenswürdigkeit von einer Netzwerkfreigabe ausgeführt werden. Der Zonenbeweis <xref:System.Security.SecurityZone.MyComputer> wird automatisch zu Assemblys hinzugefügt, die aus einer Intranetfreigabe geladen wurden. Durch diesen Beweis erhalten alle Assemblys den gleichen Satz an Berechtigungen (normalerweise volles Vertrauen) wie die Assemblys, die sich auf dem Computer befinden. Diese Funktion gilt nicht für ClickOnce-Anwendungen oder für Anwendungen, die dafür entwickelt wurden, auf einem Host ausgeführt zu werden.  
  
## <a name="rules-for-library-assemblies"></a>Regeln für Bibliothekassemblys  

Die folgenden Regeln gelten für Assemblys, die von einer ausführbaren Datei in einer Netzwerkfreigabe geladen wurden:  
  
- Bibliotheksassemblys müssen sich im gleichen Ordner wie die ausführbaren Assemblys befinden. Assemblys, die sich in einem Unterordner befinden oder auf die mit einem anderen Pfad verwiesen wird, erhalten nicht das Berechtigungsset des vollen Vertrauens.  
  
- Wenn die ausführbare Datei eine Assembly verzögert lädt, muss es den gleichen Pfad verwenden, der beim Starten der ausführbaren Datei verwendet wurde. Wenn z.B. die Freigabe \\\\*network-computer*\\*share* einem Laufwerkbuchstaben zugeordnet wird und die ausführbare Datei von diesem Pfad ausgeführt wird, erhalten Assemblys, die von der ausführbaren Datei mithilfe des Netzwerkpfads geladen werden, kein volles Vertrauen. Um eine Assembly in der <xref:System.Security.SecurityZone.MyComputer>-Zone verzögert zu laden, muss die ausführbare Datei den Pfad des Laufwerkbuchstabens verwenden.  
  
## <a name="restoring-the-former-intranet-policy"></a>Wiederherstellen der vorherigen Intranetrichtlinie  

In früheren Versionen von .NET Framework wurden freigegebenen Assemblys <xref:System.Security.SecurityZone.Intranet>-Zonenbeweise erteilt. Sie mussten die Codezugriffs-Sicherheitsrichtlinie angeben, um Assemblys einer Freigabe volles Vertrauen zu erteilen.  
  
Dieses neue Verhalten ist das Standardverhalten für Intranetassemblys. Sie können das vorherige Verhalten (das Angeben von <xref:System.Security.SecurityZone.Intranet>-Beweisen), indem Sie einen Registrierungsschlüssel festlegen, der für alle Anwendungen auf dem Computer gilt. Dieser Prozess ist für 32-Bit- und 64-Bit-Computer unterschiedlich:  
  
- Erstellen Sie auf 32-Bit-Computern einen Unterschlüssel unter dem Schlüssel „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework“ in der Registrierung des Systems. Verwenden Sie den Schlüsselnamen „LegacyMyComputerZone“ mit einem DWORD-Wert von 1.  
  
- Erstellen Sie auf 64-Bit-Computern einen Unterschlüssel unter dem Schlüssel „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework“ in der Registrierung des Systems. Verwenden Sie den Schlüsselnamen „LegacyMyComputerZone“ mit einem DWORD-Wert von 1. Erstellen Sie den gleichen Unterschlüssel unter dem Schlüssel „HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework“.  
  
## <a name="see-also"></a>Siehe auch

- [Programmieren mit Assemblys](../../standard/assembly/index.md)
