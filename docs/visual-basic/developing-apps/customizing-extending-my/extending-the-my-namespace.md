---
title: Erweitern des My-Namespaces in Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 4d7bb6eef398746a4bd2dc4dbf3d526da1c1e0f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814154"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Erweitern des My-Namespaces in Visual Basic
Die `My` Namespaces in Visual Basic verfügbar macht, Eigenschaften und Methoden, mit denen Sie problemlos von der Leistungsfähigkeit von .NET Framework nutzen können. Die `My` Namespace vereinfacht häufige Programmierprobleme, häufig eine schwierige Aufgabe auf eine einzige Zeile Code zu reduzieren. Darüber hinaus die `My` Namespace ist vollständig erweiterbar, sodass Sie das Verhalten anpassen können `My` und seiner Hierarchie zur Anpassung an die spezifischen Anforderungen Ihrer Anwendung neue Dienste hinzugefügt. Beide in diesem Thema Anpassen von vorhandenen Mitglieder der `My` Namespace und wie Sie eigene benutzerdefinierten Klassen zum Hinzufügen der `My` Namespace.  
  
 **Inhalt des Themas**  
  
-   [Anpassen von vorhandenen meinen Namespace-Elemente](#customizing)  
  
-   [Hinzufügen von Mitgliedern zu Meine Objekte](#addingtoobjects)  
  
-   [Hinzufügen von benutzerdefinierten Objekten, die meinen Namespace](#addingcustom)  
  
-   [Hinzufügen von Elementen, die meinen Namespace](#addingtonamespace)  
  
-   [Hinzufügen von Ereignissen zu benutzerdefinierten My-Objekten](#addingevents)  
  
-   [Richtlinien für den Entwurf](#design)  
  
-   [Entwerfen von Klassenbibliotheken für meine](#designing)  
  
-   [Verpacken und Bereitstellen von Erweiterungen](#packaging)  
  
## <a name="customizing"></a> Anpassen von vorhandenen meinen Namespace-Elemente  
 Die `My` -Namespace in Visual Basic stellt häufig verwendete Informationen über Ihre Anwendung und Ihrem Computer. Eine vollständige Liste der Objekte in der `My` -Namespace finden Sie unter [My Reference](../../../visual-basic/language-reference/keywords/my-reference.md). Möglicherweise müssen Sie die vorhandenen Mitglieder der Anpassen der `My` Namespace, damit sie besser entsprechen die Anforderungen Ihrer Anwendung. Jede Eigenschaft eines Objekts in der `My` Namespace, der nicht schreibgeschützt ist, kann auf einen benutzerdefinierten Wert festgelegt werden.  
  
 Nehmen wir beispielsweise an, dass Sie häufig verwenden die `My.User` Objekt, das den aktuellen Sicherheitskontext für den Benutzer, die Ausführung Ihrer Anwendung zuzugreifen. Allerdings verwendet Ihr Unternehmen ein benutzerdefiniertes Objekt, um zusätzliche Informationen und Funktionen für Benutzer innerhalb des Unternehmens verfügbar zu machen. In diesem Szenario können Sie den Standardwert ersetzen die `My.User.CurrentPrincipal` Eigenschaft mit einer Instanz von Ihren eigenen benutzerdefinierten Prinzipalobjekts, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]  
  
 Festlegen der `CurrentPrincipal` Eigenschaft für die `My.User` Objekt ändert, die Identität, unter denen die Anwendung ausgeführt wird. Die `My.User` Objekt wiederum gibt Informationen zu den neu angegebenen Benutzer zurück.  
  
## <a name="addingtoobjects"></a> Hinzufügen von Mitgliedern zu Meine Objekte  
 Die Typen von zurückgegebenen `My.Application` und `My.Computer` sind definiert als `Partial` Klassen. Daher können Sie erweitern die `My.Application` und `My.Computer` Objekte durch das Erstellen einer `Partial` Klasse mit dem Namen `MyApplication` oder `MyComputer`. Die Klasse kann keinem `Private` Klasse. Bei Angabe von der Klasse als Teil der `My` -Namespace können Sie hinzufügen, Eigenschaften und Methoden, die enthalten sind die `My.Application` oder `My.Computer` Objekte.  
  
 Im folgenden Beispiel wird z. B. eine Eigenschaft namens `DnsServerIPAddresses` auf die `My.Computer` Objekt.  
  
 [!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]  
  
## <a name="addingcustom"></a> Hinzufügen von benutzerdefinierten Objekten, die meinen Namespace  
 Obwohl die `My` Namespace bietet Lösungen für viele gängige Programmieraufgaben erledigen, treten ggf. die Aufgaben, die die `My` Namespace befasst sich nicht. Z. B. kann benutzerdefinierte Verzeichnisdienste für Benutzerdaten auf Ihre Anwendung zugreifen kann, oder Ihre Anwendung Assemblys, die standardmäßig mit Visual Basic nicht installiert werden. Sie können die erweitern die `My` Namespace, um benutzerdefinierte Lösungen für häufige Aufgaben enthalten, die für Ihre Umgebung spezifisch sind. Die `My` Namespace kann problemlos erweitert werden, um neue Member, um die wachsende Anwendung Bedürfnissen hinzufügen. Sie können darüber hinaus Bereitstellen Ihrer `My` Namespaceerweiterungen an andere Entwickler als Visual Basic-Vorlage.  
  
### <a name="addingtonamespace"></a> Hinzufügen von Elementen, die meinen Namespace  
 Da `My` ist ein Namespace wie allen anderen Namespaces können Sie Eigenschaften der obersten Ebene, hinzufügen, indem nur ein Modul und geben Sie einen `Namespace` von `My`. Kommentieren Sie das Modul mit dem `HideModuleName` -Attribut wie im folgenden Beispiel gezeigt. Die `HideModuleName` Attribut wird sichergestellt, dass IntelliSense nicht den Namen des Moduls angezeigt wird, die Mitglieder der Anzeige der `My` Namespace.  
  
 [!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]  
  
 Zum Hinzufügen von Mitgliedern zu den `My` -Namespace, fügen Sie die Eigenschaften für das Modul nach Bedarf hinzu. Für jede Eigenschaft, die hinzugefügt, der `My` -Namespace, fügen Sie ein privates Feld vom Typ `ThreadSafeObjectProvider(Of T)`, wobei der Typ der von die benutzerdefinierte Eigenschaft zurückgegebene Typ ist. Dieses Feld wird zum Erstellen von threadsicheren Objektinstanzen, die von der Eigenschaft, die durch den Aufruf zurückgegeben werden, verwendet der `GetInstance` Methode. Daher erhält jeder Thread, der die erweiterte Eigenschaft zugreift, eine eigene Instanz des zurückgegebenen Typs. Das folgende Beispiel fügt eine Eigenschaft namens `SampleExtension` vom Typ `SampleExtension` auf die `My` Namespace:  
  
 [!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]  
  
## <a name="addingevents"></a> Hinzufügen von Ereignissen zu benutzerdefinierten My-Objekten  
 Können Sie die `My.Application` Objekt, das Ereignisse für benutzerdefinierte verfügbar zu machen `My` Objekte durch die Erweiterung der `MyApplication` partielle Klasse in der `My` Namespace. Sie können für Windows-basierten Projekten Doppelklicken der **Mein Projekt** Knoten für das Projekt im **Projektmappen-Explorer**. In der Visual Basic **Projekt-Designer**, klicken Sie auf die `Application` Registerkarte, und klicken Sie dann auf die `View Application Events` Schaltfläche. Eine neue Datei mit dem Namen "ApplicationEvents.vb" wird erstellt. Sie enthält den folgenden Code zum Erweitern der `MyApplication` Klasse.  
  
 [!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]  
  
 Sie können Ereignishandler hinzufügen, für die benutzerdefinierte `My` Objekte durch das Hinzufügen benutzerdefinierter Ereignishandler auf der `MyApplication` Klasse. Benutzerdefinierte Ereignisse können Sie Code hinzufügen, der ausgeführt wird, wenn ein Ereignishandler hinzugefügt, entfernt, oder das Ereignis wird ausgelöst. Beachten Sie, dass die `AddHandler` code für ein benutzerdefiniertes Ereignis, das ausgeführt wird, nur dann, wenn Code von einem Benutzer für die Ereignisbehandlung hinzugefügt wird. Betrachten Sie beispielsweise, die die `SampleExtension` Objekt aus dem vorherigen Abschnitt hat eine `Load` -Ereignis, das Sie für einen benutzerdefinierten Ereignishandler hinzufügen möchten. Das folgende Codebeispiel zeigt einen benutzerdefinierten Ereignishandler namens `SampleExtensionLoad` , werden aufgerufen wird, wenn die `My.SampleExtension.Load` Ereignis auftritt. Wenn der Code zum Behandeln des neuen hinzugefügt wird `My.SampleExtensionLoad` -Ereignis, das `AddHandler` Teil dieses Codes benutzerdefiniertes Ereignis ausgeführt wird. Die `MyApplication_SampleExtensionLoad` Methode befindet sich im Codebeispiel wird ein Beispiel für einen Ereignishandler angezeigt, die behandelt die `My.SampleExtensionLoad` Ereignis. Beachten Sie, dass die `SampleExtensionLoad` Ereignis werden zur Verfügung stehen, bei der Auswahl der **Meine Anwendungsereignisse** -Option in der linken Dropdownliste oberhalb des Code-Editors beim Bearbeiten der Datei "ApplicationEvents.vb" hinzu.  
  
 [!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]  
  
## <a name="design"></a> Richtlinien für den Entwurf  
 Bei der Entwicklung von Erweiterungen für die `My` -Namespace, verwenden Sie die folgenden Richtlinien, um die Wartungskosten Ihrer Erweiterung-Komponenten zu minimieren.  
  
-   **Nur die Erweiterungslogik enthalten sein.** Die Logik enthalten, die der `My` Namespaceerweiterung sollte nur den Code, der erforderlich ist, um die erforderlichen Funktionen im verfügbar zu machen enthalten die `My` Namespace. Da Ihre Erweiterung als Quellcode in Benutzerprojekten befinden soll, aktualisieren die Erweiterungskomponente verursacht eine hohe Wartungskosten und sollte möglichst vermieden werden.  
  
-   **Minimieren Sie die Projektannahmen.** Bei der Erstellung Ihrer Erweiterungen von der `My` -Namespace, gehen Sie keine Reihe von verweisen, auf Projektebene importiert oder bestimmten Compiler-Einstellungen (z. B. `Option Strict` deaktiviert). Stattdessen Abhängigkeiten zu minimieren und vollqualifizierten Verweise auf alle Typen mit den `Global` Schlüsselwort. Stellen Sie außerdem sicher, dass die Erweiterung mit kompiliert `Option Strict` auf, um Fehler in der Erweiterung zu minimieren.  
  
-   **Isolieren Sie den Code der Erweiterung.** Platzieren den Code in einer einzelnen Datei ist die Erweiterung ganz einfach als eine Elementvorlage für Visual Studio bereitgestellt. Weitere Informationen finden Sie unter "Verpacken und Bereitstellen von Erweiterungen" weiter unten in diesem Thema. Platzieren alle der `My` Namespace Erweiterungscode in einer einzelnen Datei oder einen separaten Ordner in einem Projekt hilft auch Benutzer finden das `My` Namespace-Erweiterung.  
  
## <a name="designing"></a> Entwerfen von Klassenbibliotheken für meine  
 Wie bei den meisten Objektmodelle der Fall ist, funktionieren einige Entwurfsmuster in der `My` -Namespace und andere nicht der Fall ist. Beim Entwerfen einer Erweiterung für die `My` -Namespace, sollten Sie die folgenden Prinzipien:  
  
-   **Zustandslose Methoden.** Methoden in der `My` Namespace sollten bereitstellen eine gesamtlösung für eine bestimmte Aufgabe. Stellen Sie sicher, dass die Werte der Parameter, die an die Methode übergeben werden alle Eingaben erforderlich, um die jeweilige Aufgabe angeben. Vermeiden Sie das Erstellen von Methoden, die auf früheren Status, beispielsweise Öffnen von Verbindungen mit Ressourcen basieren.  
  
-   **Globale Instanzen.** Der einzige Zustand beibehalten wird, die die `My` -Namespace ist global für das Projekt. Z. B. `My.Application.Info` kapselt Zustand, in der gesamten Anwendung verwendet wird.  
  
-   **Einfache Parametertypen.** Ihre Umgebung einfach durch das Vermeiden der komplexer Parametertypen. Erstellen Sie stattdessen die Methoden, die entweder keine Parameter eingeben werden oder einfache Eingabetypen wie z. B. Zeichenfolgen, primitive Typen und So weiter.  
  
-   **Factorymethoden.** Einige Typen sind unbedingt schwierig ist, zu instanziieren. Bereitstellung von Factorymethoden als Erweiterungen der `My` Namespace ermöglicht es Ihnen leichter ermitteln und nutzen Typen, die in diese Kategorie fallen. Ist ein Beispiel für eine Factorymethode, die gut funktioniert `My.Computer.FileSystem.OpenTextFileReader`. Verschiedene Streamtypen sind in .NET Framework verfügbar. Durch Angabe von Textdateien insbesondere die `OpenTextFileReader` können die Benutzer wissen, welcher Stream verwenden.  
  
 Diese Richtlinien sind Allgemeine Entwurfsprinzipien für Klassenbibliotheken nicht ausgeschlossen. Vielmehr handelt es sich Empfehlungen, die für Entwickler optimiert sind, die Visual Basic verwenden und die `My` Namespace. Allgemeine Entwurfsprinzipien für das Erstellen von Klassenbibliotheken, finden Sie unter [Framework-Entwurfsrichtlinien](../../../standard/design-guidelines/index.md).  
  
## <a name="packaging"></a> Verpacken und Bereitstellen von Erweiterungen  
 Sie können einschließen `My` Namespaceerweiterungen in einer Visual Studio-Projektvorlage, oder Sie können Ihrer Erweiterungen Verpacken und als eine Elementvorlage für Visual Studio bereitzustellen. Wenn Sie Packen Ihrer `My` Namespaceerweiterungen als Visual Studio-Elementvorlage, profitieren Sie von den Funktionsumfang von Visual Basic bereitgestellt. Diese Funktionen ermöglichen es Ihnen, eine Durchwahl einzuschließen, wenn ein Projekt auf eine bestimmte Assembly verweist, oder aktivieren Sie die Benutzer explizit hinzufügen Ihrer `My` Namespaceerweiterung mithilfe der **My-Erweiterungen** Seite der Visual Basic Projekt-Designer.  
  
 Ausführliche Informationen zum Bereitstellen von `My` Namespaceerweiterungen finden Sie unter [Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md).  
  
## <a name="see-also"></a>Siehe auch

- [Packen und Bereitstellen von benutzerdefinierten My-Erweiterungen](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)
- [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [My-Erweiterungen-Seite im Projekt-Designer](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [Seite „Anwendung“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Partial](../../../visual-basic/language-reference/modifiers/partial.md)
