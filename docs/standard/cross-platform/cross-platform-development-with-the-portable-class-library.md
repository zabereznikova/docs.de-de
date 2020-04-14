---
title: Plattformübergreifende Entwicklung mit der portablen Klassenbibliothek
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
ms.openlocfilehash: 7caddd7361b8f364762fb4357e35cb918ae99263
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242802"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a>Plattformübergreifende Entwicklung mit der Portable Class Library

Mit dem Projekttyp "Portable Class Library" in Visual Studio können Sie plattformübergreifende Apps und Bibliotheken für Microsoft-Plattformen schnell und einfach erstellen.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

Portable Klassenbibliotheken können den Zeit- und Kostenaufwand für die Entwicklung und das Testen von Code verringern. Verwenden Sie diesen Projekttyp, um portable .NET Framework-Assemblys zu schreiben und zu erstellen, und verweisen Sie dann auf diese Assemblys von Apps, die auf mehrere Plattformen wie .NET Framework, iOS oder Mac abzielen.

Auch nachdem Sie ein Projekt für eine portable Klassenbibliothek in Visual Studio erstellt haben und mit dem Entwickeln beginnen, können Sie die Zielplattformen noch ändern. Visual Studio kompiliert Ihre Bibliothek mit den neuen Assemblys, mit denen Sie die Änderungen identifizieren können, die Sie im Code vornehmen müssen.

## <a name="create-a-portable-class-library-project"></a>Erstellen eines Portable Class Library-Projekts

Um eine portable Klassenbibliothek zu erstellen, verwenden Sie die in Visual Studio bereitgestellte Vorlage. Erstellen Sie ein neues Projekt (**Datei** > **neues Projekt**), und wählen Sie im Dialogfeld Neues **Projekt** Ihre Programmiersprache (Visual C oder Visual Basic) aus. Wählen Sie dann die Vorlage **Klassenbibliothek (Legacy Portable)** aus. Geben Sie einen Namen für Ihr Projekt ein, und wählen Sie **OK**.

Das Dialogfeld **Portable Klassenbibliothek hinzufügen** wird angezeigt. Wählen Sie zwei oder mehr Ziele aus, und wählen Sie dann **OK**.

![Hinzufügen von portablen Klassenbibliothekszielen in Visual Studio](media/add-portable-class-library.png)

## <a name="change-targets"></a>Änderungsziele

Sie können die Zielplattformen eines tragbaren Klassenbibliotheksprojekts ändern, wenn Sie es erstellen oder nachdem Sie mit der Entwicklung begonnen haben. Wenn Sie die Ziele ändern möchten, nachdem Sie das Projekt erstellt haben, öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für Ihr Projekt "Portable Class Library" (nicht die Projektmappe), und wählen Sie dann **Eigenschaften**aus. Auf der Seite Projekteigenschaften werden auf der Registerkarte **Bibliothek** die Plattformen angezeigt, auf die Ihr Projekt derzeit abzielt.

![Projekteigenschaften für Portable Class Library in Visual Studio](media/pcl-project-properties.png)

Um Ziele hinzuzufügen oder zu entfernen, wählen Sie die Schaltfläche **Ändern** aus, und deaktivieren Sie dann die entsprechenden Kontrollkästchen, und deaktivieren Sie sie.

Wenn Sie die Zielplattformen ändern, passen sich auch die APIs, die Ihnen zum Entwickeln des Projekts zur Verfügung stehen, Ihrer Auswahl an. Visual Studio meldet die Fehler und Warnungen, die durch den Wechsel der Zielplattformen entstehen können.

Wenn Sie die Portabilität Ihrer Assemblys auswerten möchten, bevor Sie Änderungen in Visual Studio vornehmen, können Sie [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)verwenden.

## <a name="supported-types-and-members"></a>Unterstützte Typen und Members

Die Typen und Member, die in Projekten für portable Klassenbibliotheken verfügbar sind, werden von mehreren Kompatibilitätsfaktoren beschränkt:

- Sie müssen von allen Zielen, die Sie ausgewählt haben, gemeinsam nutzbar sein.

- Sie müssen sich auf diesen Zielen in ähnlicher Weise verhalten.

- Sie dürfen keine Kandidaten für Veraltung sein.

- Sie müssen jedoch in einer übertragbaren Umgebung einen Sinn ergeben, insbesondere wenn sie nicht übertragbare Member unterstützen.

Wird ein Member in der portablen Klassenbibliothek und für Ihre Ziele unterstützt, erscheint es in Ihrem Projekt in IntelliSense. Beachten Sie aber, dass eine API zwar in der portablen Klassenbibliothek unterstützt werden kann, ob Sie die API jedoch verwenden können, hängt von den gewählten Zielen ab.

## <a name="api-differences-in-the-portable-class-library"></a>API-Unterschiede in der portablen Klassenbibliothek

Um die Kompatibilität von Assemblys für portable Klassenbibliotheken mit allen unterstützten Plattformen sicherzustellen, wurden einige Member in der portablen Klassenbibliothek geringfügig geändert.

## <a name="use-the-portable-class-library"></a>Verwenden der Portable Class Library

Nachdem Sie das Projekt für die portable Klassenbibliothek erstellt haben, verweisen Sie einfach aus anderen Projekten auf das neue Projekt. Sie können entweder auf das Projekt oder auf bestimmte Assemblys verweisen, die die Klassen enthalten, auf die Sie zugreifen möchten.

Um eine App auszuführen, die auf die Assembly einer portablen Klassenbibliothek verweist, müssen auf dem Computer die erforderlichen Versionen (oder höhere Versionen) der Zielplattformen installiert sein. Visual Studio enthält alle erforderlichen Frameworks, sodass Sie die App ohne weitere Änderung auf dem Computer ausführen können, auf dem Sie die Anwendung entwickelt haben.

### <a name="deploy-a-universal-windows-app"></a>Bereitstellen einer universellen Windows-App

Wenn Sie eine universelle Windows-App erstellen, die auf eine Portable Class Library-Assembly verweist, ist alles, was Sie zum Bereitstellen der App benötigen, im App-Paket enthalten, und es sind keine weiteren Schritte erforderlich.

### <a name="deploy-a-net-framework-app"></a>Bereitstellen einer .NET Framework-App

Wenn Sie eine .NET Framework-App bereitstellen, die auf eine Assembly einer portablen Klassenbibliothek verweist, müssen Sie eine Abhängigkeit von der richtigen Version von .NET Framework angeben. Durch die Angabe dieser Abhängigkeit stellen Sie sicher, dass die erforderliche Version mit der App installiert wird.

- Um eine Abhängigkeit mit ClickOnce-Bereitstellung zu erstellen: Wählen Sie im **Projektmappen-Explorer**den Projektknoten für das Projekt aus, das Sie veröffentlichen möchten. (Dies ist das Projekt, das auf das Projekt "Portable Class Library" verweist.) Wählen Sie in der Menüleiste > **Projekteigenschaften**aus, und wählen Sie dann die Registerkarte **Veröffentlichen** aus. **Project** Wählen Sie auf der **Seite Veröffentlichen** die Option **Voraussetzungen**aus. Wählen Sie die erforderliche .NET Framework-Version als erforderliche Komponente aus.

- So erstellen Sie eine Abhängigkeit mit einem Setupprojekt: Wählen Sie im **Projektmappen-Explorer**das Setupprojekt aus. Wählen Sie in der Menüleiste > **Projekteigenschaftenvoraussetzungen** > **Prerequisites**aus. **Project** Wählen Sie die erforderliche .NET Framework-Version als erforderliche Komponente aus.

Weitere Informationen zum Bereitstellen von .NET Framework-Apps finden Sie im [Bereitstellungshandbuch für Entwickler](../../../docs/framework/deployment/deployment-guide-for-developers.md).

## <a name="see-also"></a>Siehe auch

- [Verwenden der portablen Klassenbibliothek mit MVVM](using-portable-class-library-with-model-view-view-model.md)
- [App-Ressourcen für Bibliotheken, die auf mehrere Plattformen abzielen](app-resources-for-libraries-that-target-multiple-platforms.md)
- [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [Bereitstellung](../../../docs/framework/deployment/net-framework-applications.md)
