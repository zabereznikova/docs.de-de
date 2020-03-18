---
title: Richtlinien für die Erstellung von Komponenten für die parallele Ausführung
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, multiple application versions
- side-by-side execution, multiple component versions
ms.assetid: 5c540161-6e40-42e9-be92-6175aee2c46a
ms.openlocfilehash: 42d0e2d85517d4a8fb443db9b63e6b893267caca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121584"
---
# <a name="guidelines-for-creating-components-for-side-by-side-execution"></a>Richtlinien für die Erstellung von Komponenten für die parallele Ausführung
Befolgen Sie die nachstehenden allgemeinen Richtlinien zum Erstellen von verwalteten Anwendungen oder Komponenten, die für die parallele Ausführung entwickelt wurden:  
  
- Binden Sie die Typidentität an eine bestimmte Version einer Datei.  
  
     Die Common Language Runtime bindet die Typidentität mithilfe von Assemblys mit starken Namen an eine bestimmte Dateiversion. Um eine Anwendung oder Komponente für die parallele Ausführung zu erstellen, müssen Sie allen Assemblys einen starken Namen zuweisen. Auf diese Weise wird eine genaue Typidentität erstellt und sichergestellt, dass jede Typauflösung zur richtigen Datei geleitet wird. Eine Assembly mit starkem Namen enthält Informationen zu Version, Kultur und Verleger, anhand der die Common Language Runtime die richtige Datei zur Erfüllung einer Bindungsanforderung sucht.  
  
- Verwenden Sie die versionsabhängige Speicherung.  
  
     Die Laufzeit verwendet den globalen Assemblycache, um versionsabhängige Speicherung bereitzustellen. Der globale Assemblycache ist eine versionsabhängige Verzeichnisstruktur, die auf jedem Computer installiert ist, der .NET Framework verwendet. Im globalen Assemblycache installierte Assemblys werden nicht überschrieben, wenn eine neue Version der Assembly installiert wird.  
  
- Erstellen Sie eine Anwendung oder Komponente, die isoliert ausgeführt wird.  
  
     Eine isoliert ausgeführte Anwendung oder Komponente muss Ressourcen verwalten, um Konflikte zu vermeiden, wenn zwei Instanzen der Anwendung oder Komponente gleichzeitig ausgeführt werden. Die Anwendung oder Komponente muss außerdem eine versionsspezifische Dateistruktur verwenden.  
  
## <a name="application-and-component-isolation"></a>Anwendungs- und Komponentenisolierung  
 Der Schlüssel zum erfolgreichen Entwerfen von Anwendungen oder Komponenten für die parallele Ausführung ist die Isolation. Die Anwendung oder Komponente muss alle Ressourcen, insbesondere die Datei-E/A, isoliert verwalten. Befolgen Sie die nachstehenden Richtlinien, um sicherzustellen, dass die Anwendung oder Komponente isoliert ausgeführt wird:  
  
- Schreiben Sie versionsspezifische Werte in die Registrierung. Speichern Sie die Werte in Strukturen oder Schlüsseln, die die Version angeben, und nutzen Sie Informationen oder Zustände nicht gemeinsam für mehrere Versionen einer Komponente. Dies verhindert, dass zwei Anwendungen oder Komponenten, die gleichzeitig ausgeführt werden, Informationen überschreiben.  
  
- Machen Sie benannte Kernelobjekte versionsspezifisch, sodass keine Racebedingung auftritt. Eine Racebedingung tritt z. B. auf, wenn zwei Semaphore zweier verschiedener Versionen derselben Anwendung aufeinander warten.  
  
- Machen Sie Datei- und Verzeichnisnamen versionsabhängig. Dies bedeutet, dass Dateistrukturen auf Versionsinformationen beruhen sollten.  
  
- Erstellen Sie Benutzerkonten und Gruppen auf versionsspezifische Weise. Benutzerkonten und Gruppen, die von einer Anwendung erstellt wurden, sollten nach Version identifiziert werden. Nutzen Sie Informationen oder Zustände nicht gemeinsam für mehrere Versionen einer Komponente.  
  
## <a name="installing-and-uninstalling-versions"></a>Installieren und Deinstallieren von Versionen  
 Beim Entwerfen einer Anwendung für die parallele Ausführung befolgen Sie die nachstehenden Richtlinien zum Installieren und Deinstallieren von Versionen:  
  
- Löschen Sie keine Informationen aus der Registrierung, die möglicherweise von anderen Anwendungen benötigt werden, die unter einer anderen Version von .NET Framework ausgeführt werden.  
  
- Ersetzen Sie keine Informationen in der Registrierung, die möglicherweise von anderen Anwendungen benötigt werden, die unter einer anderen Version von .NET Framework ausgeführt werden.  
  
- Löschen Sie keine Informationen aus der Registrierung, die möglicherweise von anderen Anwendungen benötigt werden, die unter einer anderen Version von .NET Framework ausgeführt werden.  
  
- Ändern Sie nicht **InprocServer32** oder andere Registrierungseinträge für einen COM-Server, der bereits registriert wurde.  
  
- Löschen Sie keine Benutzerkonten oder Gruppen aus der Registrierung, die möglicherweise von anderen Anwendungen benötigt werden, die unter einer anderen Version von .NET Framework ausgeführt werden.  
  
- Fügen Sie der Registrierung nichts hinzu, was einen Pfad ohne Versionsinformationen enthält.  
  
## <a name="file-version-number-and-assembly-version-number"></a>Dateiversionsnummer und Assemblyversionsnummer  
 Die Dateiversion ist eine Win32-Versionsressource, die nicht von der Laufzeit verwendet wird. Im Allgemeinen aktualisieren Sie die Dateiversion sogar für ein direktes Update. Zwei identische Dateien können über unterschiedliche Dateiversionsinformationen verfügen, und zwei verschiedene Dateien können die gleichen Dateiversionsinformationen aufweisen.  
  
 Die Laufzeit verwendet die Assemblyversion für die Assemblybindung. Die Laufzeit behandelt zwei identische Assemblys mit unterschiedlichen Versionsnummern als zwei verschiedene Assemblys.  
  
 Mit dem [Tool für den globalen Assemblycache (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) können Sie eine Assembly ersetzen, wenn lediglich die Dateiversionsnummer höher ist. Der Installer führt in in der Regel nur dann eine Installation über eine Assembly durch, wenn die Assemblyversionsnummer höher ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Parallele Ausführung](side-by-side-execution.md)
- [Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
