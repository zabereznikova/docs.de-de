---
title: "Gewusst wie: Simulieren von Maus- und Tastaturereignissen in Code | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Tastaturen, Ereignissimulation"
  - "Benutzereingabe, Simulieren"
  - "SendKeys, Verwendung"
  - "Mausklicks, Simulieren"
  - "Maus, Ereignissimulation"
ms.assetid: 6abcb67e-3766-4af2-9590-bf5dabd17e41
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Simulieren von Maus- und Tastaturereignissen in Code
Windows Forms stellt mehrere Optionen zur programmgesteuerten Simulation von Maus\- und Tastatureingaben bereit. Dieses Thema enthält eine Übersicht über diese Optionen.  
  
## Simulieren von Mauseingaben  
 Die beste Möglichkeit, Mauseingaben zu simulieren, ist ein Aufruf der `On`*Ereignisname*\-Methode, die das Mausereignis auslöst, die Sie simulieren möchten. Diese Option wird normalerweise nur in benutzerdefinierten Steuerelementen und Formularen unterstützt, weil die Methoden, die Ereignisse auslösen, geschützt sind und außerhalb des Steuerelements oder Formulars nicht aufgerufen werden können. Die folgenden Schritte veranschaulichen beispielsweise, wie ein Klicken mit der rechten Maustaste in Code simuliert wird.  
  
#### So klicken Sie programmgesteuert mit der rechten Maustaste  
  
1.  Erstellen Sie eine <xref:System.Windows.Forms.MouseEventArgs>\-Instanz, deren <xref:System.Windows.Forms.MouseEventArgs.Button%2A>\-Eigenschaft auf den Wert <xref:System.Windows.Forms.MouseButtons?displayProperty=fullName> festgelegt wird.  
  
2.  Rufen Sie die <xref:System.Windows.Forms.Control.OnMouseClick%2A>\-Methode mit dieser <xref:System.Windows.Forms.MouseEventArgs>\-Instanz als Argument auf.  
  
 Weitere Informationen zu benutzerdefinierten Steuerelementen finden Sie unter [Entwickeln von Windows Forms\-Steuerelementen zur Entwurfszeit](../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).  
  
 Es gibt weitere Möglichkeiten, Mauseingaben zu simulieren. Beispielsweise können Sie programmgesteuert eine Steuerelementeigenschaft festlegen, die einen Zustand darstellt, der normalerweise per Mauseingabe festgelegt wird \(etwa die <xref:System.Windows.Forms.CheckBox.Checked%2A>\-Eigenschaft des <xref:System.Windows.Forms.CheckBox>\-Steuerelements\). Sie können aber auch direkt den Delegaten aufrufen, der mit dem Ereignis verknüpft ist, das Sie simulieren möchten.  
  
## Simulieren von Tastatureingaben  
 Tastatureingaben können mit denselben Strategien simuliert werden, die hier für Mauseingaben erläutert sind. Zusätzlich stellt Windows Forms aber die <xref:System.Windows.Forms.SendKeys>\-Klasse bereit, um Tastatureingaben an die aktive Anwendung senden zu können.  
  
> [!CAUTION]
>  Wenn Ihre Anwendung für internationale Verwendung mit unterschiedlichen Tastaturen vorgesehen ist, kann ein Verwenden von <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=fullName> zu unvorhersehbaren Ergebnissen führen und sollte vermieden werden.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.SendKeys>\-Klasse wurde für .NET Framework 3.0 aktualisiert, damit sie in Anwendungen verwendet werden kann, die unter Windows Vista ausgeführt werden. Die verbesserte Sicherheit von Windows Vista \(Stichwort Benutzerkontensteuerung\) verhindert, dass die vorherige Implementierung ordnungsgemäß funktioniert.  
>   
>  Die <xref:System.Windows.Forms.SendKeys>\-Klasse ist anfällig für Probleme hinsichtlich der zeitlichen Steuerung, sodass einige Entwickler gezwungen waren, Umgehungslösungen zu finden. Die aktualisierte Implementierung ist immer noch anfällig für Probleme hinsichtlich der zeitlichen Steuerung, ist jedoch etwas schneller und erfordert möglicherweise Änderungen an den Umgehungslösungen. Die <xref:System.Windows.Forms.SendKeys>\-Klasse versucht zunächst, die vorherige Implementierung zu verwenden. Schlägt dies fehl, wird die neue Implementierung verwendet. Infolgedessen verhält sich die <xref:System.Windows.Forms.SendKeys>\-Klasse unter verschiedenen Betriebssystemen möglicherweise unterschiedlich. Verwendet die <xref:System.Windows.Forms.SendKeys>\-Klasse die neue Implementierung, wartet die <xref:System.Windows.Forms.SendKeys.SendWait%2A>\-Methode nicht auf zu verarbeitende Nachrichten, wenn diese an einen anderen Prozess gesendet werden.  
>   
>  Ist für Ihre Anwendung ein einheitliches, vom Betriebssystem unabhängiges Verhalten erforderlich, können Sie für die <xref:System.Windows.Forms.SendKeys>\-Klasse das Verwenden der neuen Implementierung erzwingen, indem Sie die folgende Anwendungseinstellung in Ihre "app.config"\-Datei einfügen.  
>   
>  `<appSettings>`  
>   
>  `<add key="SendKeys" value="SendInput"/>`  
>   
>  `</appSettings>`  
>   
>  Soll die <xref:System.Windows.Forms.SendKeys>\-Klasse gezwungen werden, die vorherige Implementierung zu verwenden, geben Sie stattdessen den Wert `"JournalHook"` an.  
  
#### So senden Sie eine Tastatureingabe an dieselbe Anwendung  
  
1.  Rufen Sie die <xref:System.Windows.Forms.SendKeys.Send%2A>\- oder die <xref:System.Windows.Forms.SendKeys.SendWait%2A>\-Methode der <xref:System.Windows.Forms.SendKeys>\-Klasse auf. Die angegebenen Tastatureingaben werden vom aktiven Steuerelement der Anwendung empfangen. Im folgenden Codebeispiel wird <xref:System.Windows.Forms.SendKeys.Send%2A> verwendet, um ein Drücken der EINGABETASTE zu simulieren, wenn der Benutzer auf die Oberfläche des Formulars doppelklickt. Für dieses Beispiel wird ein <xref:System.Windows.Forms.Form>\-Objekt mit einem einzelnen <xref:System.Windows.Forms.Button>\-Steuerelement angenommen, dessen Aktivierreihenfolge \(TabIndex\) gleich 0 ist.  
  
     [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]  
  
#### So senden Sie eine Tastatureingabe an eine andere Anwendung  
  
1.  Aktivieren Sie das Anwendungsfenster, das die Tastatureingaben empfängt, und rufen Sie dann die <xref:System.Windows.Forms.SendKeys.Send%2A>\- oder die <xref:System.Windows.Forms.SendKeys.SendWait%2A>\-Methode auf. Da keine verwaltete Methode zum Aktivieren einer anderen Anwendung vorhanden ist, müssen Sie systemeigene Windows\-Methoden verwenden, um den Fokus auf andere Anwendungen zu erzwingen. Im folgenden Codebeispiel wird ein Plattformaufruf dazu verwendet, die Methoden `FindWindow` und `SetForegroundWindow` aufzurufen, um das Anwendungsfenster Rechner zu aktivieren, und dann wird <xref:System.Windows.Forms.SendKeys.SendWait%2A> aufgerufen, um einige Berechnungselemente an Rechner zu senden.  
  
    > [!NOTE]
    >  Die richtigen Parameter des `FindWindow`\-Aufrufs, der nach der Anwendung Rechner sucht, können je nach Windows\-Version unterschiedlich sein.  Im folgenden Code wird die Anwendung Rechner unter [!INCLUDE[win7](../../../includes/win7-md.md)] gesucht. Ändern Sie unter [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] den ersten Parameter in "SciCalc". Sie können das zu Visual Studio gehörende Tool Spy\+\+ verwenden, um die richtigen Parameter zu ermitteln.  
  
     [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]  
  
## Beispiel  
 Das folgende Codebeispiel ist die vollständige Anwendung für die vorherigen Codebeispiele.  
  
 [!code-cpp[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] auf der Befehlszeile finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 [Benutzereingaben in Windows Forms](../../../docs/framework/winforms/user-input-in-windows-forms.md)