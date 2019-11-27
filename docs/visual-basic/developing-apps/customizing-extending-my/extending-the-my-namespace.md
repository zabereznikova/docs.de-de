---
title: Erweitern des My-Namespaces
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 2a7b0b84061fccd9a333a68e4a19477bd19ca4ff
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330315"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Erweitern des `My` Namespace in Visual Basic

Der `My`-Namespace in Visual Basic stellt Eigenschaften und Methoden zur Verfügung, mit denen Sie die Vorteile der .NET Framework problemlos nutzen können. Der `My`-Namespace vereinfacht häufige Programmierprobleme, wodurch eine schwierige Aufgabe häufig auf eine einzelne Codezeile reduziert wird. Außerdem ist der `My`-Namespace vollständig erweiterbar, sodass Sie das Verhalten von `My` anpassen und neue Dienste zur Hierarchie hinzufügen können, um Sie an bestimmte Anwendungsanforderungen anzupassen. In diesem Thema wird erläutert, wie vorhandene Member des `My`-Namespace angepasst werden und wie eigene benutzerdefinierte Klassen zum `My`-Namespace hinzugefügt werden.

## <a name="customizing-existing-my-namespace-members"></a>Anpassen vorhandener `My` Namespace-Member

Der `My`-Namespace in Visual Basic stellt häufig verwendete Informationen zu Ihrer Anwendung, Ihrem Computer und mehr zur Verfügung. Eine komplette Liste der Objekte im `My`-Namespace finden Sie unter [My Reference (meine Referenz](../../language-reference/keywords/my-reference.md)). Möglicherweise müssen Sie vorhandene Member des `My`-Namespace anpassen, damit Sie den Anforderungen Ihrer Anwendung besser entsprechen. Jede Eigenschaft eines Objekts im `My` Namespace, die nicht schreibgeschützt ist, kann auf einen benutzerdefinierten Wert festgelegt werden.

Nehmen Sie beispielsweise an, dass Sie häufig das `My.User`-Objekt verwenden, um auf den aktuellen Sicherheitskontext für den Benutzer zuzugreifen, der Ihre Anwendung ausgeführt hat. Ihr Unternehmen verwendet jedoch ein benutzerdefiniertes Benutzerobjekt, um zusätzliche Informationen und Funktionen für Benutzer innerhalb des Unternehmens verfügbar zu machen. In diesem Szenario können Sie den Standardwert der `My.User.CurrentPrincipal`-Eigenschaft durch eine Instanz Ihres eigenen benutzerdefinierten Prinzipal Objekts ersetzen, wie im folgenden Beispiel gezeigt:

[!code-vb[VbVbcnExtendingMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#1)]

Wenn Sie die `CurrentPrincipal`-Eigenschaft für das `My.User` Objekt festlegen, ändert sich die Identität, unter der die Anwendung ausgeführt wird. Das `My.User`-Objekt wiederum gibt Informationen zum neu angegebenen Benutzer zurück.
  
## <a name="adding-members-to-my-objects"></a>Hinzufügen von Membern zu `My` Objekten

Die von `My.Application` und `My.Computer` zurückgegebenen Typen werden als `Partial` Klassen definiert. Aus diesem Grund können Sie die Objekte `My.Application` und `My.Computer` erweitern, indem Sie eine `Partial` Klasse mit dem Namen `MyApplication` oder `MyComputer`erstellen. Die Klasse kann keine `Private` Klasse sein. Wenn Sie die-Klasse als Teil des `My`-Namespace angeben, können Sie Eigenschaften und Methoden hinzufügen, die in der `My.Application`-oder `My.Computer`-Objekte enthalten sein werden.

Im folgenden Beispiel wird dem `My.Computer`-Objekt eine Eigenschaft mit dem Namen `DnsServerIPAddresses` hinzugefügt:

[!code-vb[VbVbcnExtendingMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class2.vb#2)]

## <a name="adding-custom-objects-to-the-my-namespace"></a>Hinzufügen von benutzerdefinierten Objekten zum `My`-Namespace

Obwohl der `My`-Namespace Lösungen für viele gängige Programmieraufgaben bereitstellt, können Sie Aufgaben erkennen, die der `My`-Namespace nicht adressiert. Beispielsweise kann Ihre Anwendung auf benutzerdefinierte Verzeichnisdienste zugreifen, oder die Anwendung verwendet Assemblys, die nicht standardmäßig mit Visual Basic installiert werden. Sie können den `My`-Namespace erweitern, um benutzerdefinierte Lösungen für allgemeine Aufgaben zu integrieren, die für Ihre Umgebung spezifisch sind. Der `My`-Namespace kann problemlos erweitert werden, um neue Mitglieder hinzuzufügen, um wachsende Anwendungsanforderungen zu erfüllen. Darüber hinaus können Sie Ihre `My`-Namespace Erweiterungen für andere Entwickler als Visual Basic Vorlage bereitstellen.
  
### <a name="adding-members-to-the-my-namespace"></a>Hinzufügen von Elementen zum `My`-Namespace

Da `My` ein Namespace wie ein beliebiger anderer Namespace ist, können Sie ihm Eigenschaften der obersten Ebene hinzufügen, indem Sie einfach ein Modul hinzufügen und eine `Namespace` `My`angeben. Kommentieren Sie das Modul mit dem `HideModuleName`-Attribut, wie im folgenden Beispiel gezeigt. Das `HideModuleName`-Attribut stellt sicher, dass IntelliSense den Modulnamen nicht anzeigt, wenn die Elemente des `My`-Namespace angezeigt werden.

[!code-vb[VbVbcnExtendingMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#3)]

Um dem `My`-Namespace Elemente hinzuzufügen, fügen Sie dem Modul nach Bedarf Eigenschaften hinzu. Fügen Sie für jede Eigenschaft, die dem `My`-Namespace hinzugefügt wird, ein privates Feld vom Typ `ThreadSafeObjectProvider(Of T)`hinzu, wobei der Typ der von der benutzerdefinierten Eigenschaft zurückgegebene Typ ist. Dieses Feld wird verwendet, um Thread sichere Objektinstanzen zu erstellen, die von der-Eigenschaft zurückgegeben werden, indem die `GetInstance`-Methode aufgerufen wird. Folglich erhält jeder Thread, der auf die erweiterte Eigenschaft zugreift, eine eigene Instanz des zurückgegebenen Typs. Im folgenden Beispiel wird dem `My`-Namespace eine Eigenschaft mit dem Namen `SampleExtension` hinzugefügt, die vom Typ `SampleExtension` ist:

[!code-vb[VbVbcnExtendingMy#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#4)]

## <a name="adding-events-to-custom-my-objects"></a>Hinzufügen von Ereignissen zu benutzerdefinierten `My` Objekten

Sie können das `My.Application`-Objekt verwenden, um Ereignisse für die benutzerdefinierten `My` Objekte verfügbar zu machen, indem Sie die `MyApplication` partielle Klasse im `My`-Namespace erweitern. Für Windows-basierte Projekte können Sie in **Projektmappen-Explorer**auf den Knoten **mein Projekt** in für das Projekt doppelklicken. Klicken Sie im Visual Basic **Projekt-Designer**auf die Registerkarte **Anwendung** , und klicken Sie dann auf die Schaltfläche **Anwendungs Ereignisse anzeigen** . Eine neue Datei mit dem Namen " *ApplicationEvents. vb* " wird erstellt. Sie enthält den folgenden Code zum Erweitern der `MyApplication`-Klasse:

[!code-vb[VbVbcnExtendingMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#5)]

Sie können Ereignishandler für die benutzerdefinierten `My`-Objekte hinzufügen, indem Sie der `MyApplication`-Klasse benutzerdefinierte Ereignishandler hinzufügen. Mit benutzerdefinierten Ereignissen können Sie Code hinzufügen, der ausgeführt wird, wenn ein Ereignishandler hinzugefügt, entfernt oder das-Ereignis ausgelöst wird. Beachten Sie, dass der `AddHandler` Code für ein benutzerdefiniertes Ereignis nur ausgeführt wird, wenn der Benutzercode zur Behandlung des Ereignisses hinzufügt. Beachten Sie z. b., dass das `SampleExtension`-Objekt aus dem vorherigen Abschnitt ein `Load` Ereignis aufweist, für das Sie einen benutzerdefinierten Ereignishandler hinzufügen möchten. Das folgende Codebeispiel zeigt einen benutzerdefinierten Ereignishandler mit dem Namen `SampleExtensionLoad`, der beim Auftreten des `My.SampleExtension.Load` Ereignisses aufgerufen wird. Wenn Code zum Verarbeiten des neuen `My.SampleExtensionLoad` Ereignisses hinzugefügt wird, wird der `AddHandler` Teil dieses benutzerdefinierten Ereignis Codes ausgeführt. Die `MyApplication_SampleExtensionLoad`-Methode ist im Codebeispiel enthalten, um ein Beispiel eines Ereignis Handlers anzuzeigen, der das `My.SampleExtensionLoad`-Ereignis behandelt. Beachten Sie, dass das `SampleExtensionLoad` Ereignis verfügbar ist, wenn Sie die Option **meine Anwendungs Ereignisse** in der linken Dropdown Liste oberhalb des Code-Editors auswählen, wenn Sie die Datei " *ApplicationEvents. vb* " bearbeiten.

[!code-vb[VbVbcnExtendingMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnExtendingMy/VB/Class1.vb#6)]

## <a name="design-guidelines"></a>Entwurfs Richtlinien

Wenn Sie Erweiterungen für den `My`-Namespace entwickeln, verwenden Sie die folgenden Richtlinien, um die Wartungskosten der Erweiterungs Komponenten zu minimieren:

- **Schließen Sie nur die Erweiterungs Logik ein.** Die in der `My`-Namespace Erweiterung enthaltene Logik sollte nur den Code enthalten, der benötigt wird, um die erforderliche Funktionalität im `My`-Namespace verfügbar zu machen. Da sich Ihre Erweiterung in Benutzer Projekten als Quellcode befinden wird, entstehen beim Aktualisieren der Erweiterungs Komponente hohe Wartungskosten und sollten nach Möglichkeit vermieden werden.
- **Minimieren Sie Projekt Annahmen.** Wenn Sie die Erweiterungen des `My`-Namespace erstellen, gehen Sie nicht davon aus, dass eine Gruppe von verweisen, Importe auf Projektebene oder bestimmte Compilereinstellungen (z. b. `Option Strict` off) enthalten sind. Minimieren Sie stattdessen die Abhängigkeiten, und qualifizieren Sie alle Typverweise mit dem `Global`-Schlüsselwort vollständig. Stellen Sie außerdem sicher, dass die Erweiterung mit `Option Strict` on kompiliert wird, um Fehler in der Erweiterung zu minimieren.
- **Isolieren Sie den Erweiterungs Code.** Wenn Sie den Code in einer einzelnen Datei platzieren, kann die Erweiterung leicht als Visual Studio-Element Vorlage bereitgestellt werden. Weitere Informationen finden Sie weiter unten in diesem Thema unter "Verpacken und Bereitstellen von Erweiterungen". Wenn Sie den Code für die `My`-Namespace Erweiterung in einer einzelnen Datei oder in einem separaten Ordner in einem Projekt platzieren, können Benutzer auch die `My`-Namespace Erweiterung suchen.

## <a name="designing-class-libraries-for-my"></a>Entwerfen von Klassenbibliotheken für `My`

Wie dies bei den meisten Objekt Modellen der Fall ist, funktionieren einige Entwurfsmuster im `My`-Namespace und andere nicht. Beachten Sie beim Entwerfen einer Erweiterung für den `My`-Namespace die folgenden Prinzipien:

- **Zustands lose Methoden.** Methoden im `My`-Namespace sollten eine komplette Lösung für eine bestimmte Aufgabe bereitstellen. Stellen Sie sicher, dass die an die-Methode übergebenen Parameterwerte sämtliche Eingaben bereitstellen, die zum Ausführen der jeweiligen Aufgabe erforderlich sind. Vermeiden Sie das Erstellen von Methoden, die sich auf den vorherigen Zustand stützen, z. b. offene Verbindungen mit Ressourcen
- **Globale Instanzen.** Der einzige Status, der im `My`-Namespace verwaltet wird, ist für das Projekt Global. `My.Application.Info` kapselt z. b. den Status, der in der gesamten Anwendung gemeinsam verwendet wird.
- **Einfache Parametertypen.** Vermeiden Sie es, indem Sie komplexe Parametertypen vermeiden. Erstellen Sie stattdessen Methoden, die entweder keine Parameter Eingaben annehmen oder einfache Eingabetypen wie z. b. Zeichen folgen, primitive Typen usw. verwenden.
- **Factorymethoden.** Einige Typen sind notwendigerweise schwer zu instanziieren. Wenn Sie Factorymethoden als Erweiterungen für den `My`-Namespace bereitstellen, können Sie Typen, die in diese Kategorie fallen, leichter ermitteln und nutzen. Ein Beispiel einer Factorymethode, die gut funktioniert, ist `My.Computer.FileSystem.OpenTextFileReader`. Im .NET Framework sind mehrere Streamtypen verfügbar. Durch die Angabe von Textdateien wird der Benutzer anhand der `OpenTextFileReader` den zu verwendenden Stream besser verstehen.

Diese Richtlinien schließen keine allgemeinen Entwurfs Prinzipien für Klassenbibliotheken aus. Vielmehr handelt es sich um Empfehlungen, die für Entwickler optimiert werden, die Visual Basic und den `My`-Namespace verwenden. Allgemeine Entwurfs Prinzipien zum Erstellen von Klassenbibliotheken finden Sie unter [Framework-Entwurfs Richtlinien](../../../standard/design-guidelines/index.md).

## <a name="packaging-and-deploying-extensions"></a>Verpacken und Bereitstellen von Erweiterungen

Sie können `My`-Namespace Erweiterungen in eine Visual Studio-Projektvorlage einschließen, oder Sie können Ihre Erweiterungen verpacken und als Visual Studio-Element Vorlage bereitstellen. Wenn Sie die `My`-Namespace Erweiterungen als Visual Studio-Element Vorlage Verpacken, können Sie zusätzliche Funktionen nutzen, die von Visual Basic bereitgestellt werden. Diese Funktionen ermöglichen es Ihnen, eine Erweiterung einzubeziehen, wenn ein Projekt auf eine bestimmte Assembly verweist, oder Benutzern das explizite Hinzufügen Ihrer `My`-Namespace Erweiterung auf der Seite " **Meine Erweiterungen** " des Visual Basic Projekt-Designers.

Ausführliche Informationen zum Bereitstellen von `My`-Namespace Erweiterungen finden Sie unter packen und Bereitstellen von [benutzerdefinierten My-Erweiterungen](packaging-and-deploying-custom-my-extensions.md).

## <a name="see-also"></a>Siehe auch

- [Packen und Bereitstellen von benutzerdefinierten My-Erweiterungen](packaging-and-deploying-custom-my-extensions.md)
- [Erweitern des Visual Basic-Anwendungsmodells](extending-the-visual-basic-application-model.md)
- [Anpassen der verfügbaren Objekte in „My“](customizing-which-objects-are-available-in-my.md)
- [My-Erweiterungen-Seite im Projekt-Designer](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
- [Seite "Anwendung", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Partial](../../language-reference/modifiers/partial.md)
