---
title: 'Vorgehensweise: Verknüpfen mit einem Delegaten mit Reflektion'
description: So verknüpfen Sie einen Delegaten mit Reflexion in .NET. Verbinden Sie eine vorhandene Methode mit einem Ereignis, indem Sie die erforderlichen Typen über Reflexion erhalten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], adding event handlers with reflection
- reflection, adding event-handler delegates
- delegates [.NET Framework], adding event handlers with reflection
ms.assetid: 076ee62d-a964-449e-a447-c31b33518b81
ms.openlocfilehash: 9a92afd1c2aeadeb0cf7bc1e626b5bd1fb3cecea
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263424"
---
# <a name="how-to-hook-up-a-delegate-using-reflection"></a>Vorgehensweise: Verknüpfen mit einem Delegaten mit Reflektion

Wenn Sie Assemblys mithilfe von Reflektion laden und ausführen, können Sie Ereignisse nicht mit Sprachfunktionen wie dem Operator `+=` von C# oder der [AddHandler-Anweisung](../../visual-basic/language-reference/statements/addhandler-statement.md) von Visual Basic verknüpfen. In den folgenden Verfahrensweisen wird veranschaulicht, wie eine vorhandene Methode mit einem Ereignis verknüpft wird, indem alle erforderlichen Typen über Reflektion abgerufen werden, und wie eine dynamische Methode mithilfe von Reflektionsausgabe erstellt und mit einem Ereignis verknüpft wird.  
  
> [!NOTE]
> Eine andere Möglichkeit, einen Delegaten für die Ereignisbehandlung zu verknüpfen, zeigt das Codebeispiel für die <xref:System.Reflection.EventInfo.AddEventHandler%2A>-Methode der <xref:System.Reflection.EventInfo>-Klasse.  
  
### <a name="to-hook-up-a-delegate-using-reflection"></a>So verknüpfen Sie einen Delegaten mithilfe von Reflektion  
  
1. Laden Sie eine Assembly, die einen Typ enthält, der Ereignisse auslöst. Assemblys werden üblicherweise anhand der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode geladen. Um dieses Beispiel möglichst einfach zu halten, wird ein abgeleitetes Formular in der aktuellen Assembly verwendet, es wird daher die <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>-Methode zum Laden der aktuellen Assembly verwendet.  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2. Rufen Sie ein <xref:System.Type>-Objekt ab, das den Typ darstellt, und erstellen Sie eine Instanz des Typs. Da das Formular über einen parameterlosen Konstruktor verfügt, wird im folgenden Code die Methode <xref:System.Activator.CreateInstance%28System.Type%29> verwendet. Es gibt verschiedene andere Überladungen der Methode <xref:System.Activator.CreateInstance%2A>, die Sie verwenden können, wenn der erstellte Typ nicht über einen parameterlosen Konstruktor verfügt. Die neue Instanz wird als Typ <xref:System.Object> gespeichert, um bei der Idee zu bleiben, dass keine Informationen über die Assembly bekannt sind. (Mithilfe der Reflektion können Sie die Typen in einer Assembly abrufen, ohne ihre Namen bereits zu kennen.)  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3. Rufen Sie ein <xref:System.Reflection.EventInfo>-Objekt ab, dass das Ereignis darstellt, und rufen Sie mithilfe der <xref:System.Reflection.EventInfo.EventHandlerType%2A>-Eigenschaft den Typ des Delegaten ab, der für die Ereignisbehandlung verwendet wird. Im folgenden Code wird ein <xref:System.Reflection.EventInfo> für das <xref:System.Windows.Forms.Control.Click>-Ereignis abgerufen.  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4. Rufen Sie ein <xref:System.Reflection.MethodInfo>-Objekt ab, das die Methode darstellt, die das Ereignis behandelt. Der vollständige Programmcode im Thema "Beispiel" weiter unten enthält eine Methode, die der Signatur des <xref:System.EventHandler>-Delegaten entspricht, der das <xref:System.Windows.Forms.Control.Click>-Ereignis behandelt, zur Laufzeit können Sie auch dynamische Methoden generieren. Einzelheiten finden Sie in der zugehörigen Prozedur zum Generieren eines Ereignishandlers zur Laufzeit durch eine dynamische Methode.  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5. Erstellen Sie mithilfe der <xref:System.Delegate.CreateDelegate%2A>-Methode eine Instanz des Delegaten. Diese Methode ist statisch (`Shared` in Visual Basic), daher muss der Delegattyp angegeben werden. Es empfiehlt sich, die Überladungen von <xref:System.Delegate.CreateDelegate%2A> zu verwenden, die eine <xref:System.Reflection.MethodInfo> akzeptieren.  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6. Rufen Sie die `add`-Accessormethode ab, und rufen Sie sie auf, auf das Ereignis zu verknüpfen. Alle Ereignisse verfügen über einen `add`-Accessor und einen `remove`-Accessor, die durch die Syntax hoch entwickelter Sprachen verborgen sind. Ereignisse werden beispielsweise in C# mit dem Operator `+=` und in Visual Basic mit der [AddHandler-Anweisung](../../visual-basic/language-reference/statements/addhandler-statement.md) verknüpft. Im folgenden Code wird der `add`-Accessor des <xref:System.Windows.Forms.Control.Click>-Ereignisses abgerufen und dieses dann spät gebunden aufgerufen, indem die Delegatinstanz übergeben wird. Die Argumente müssen als Array übergeben werden.  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7. Testen Sie das Ereignis. Im folgenden Code wird das im Codebeispiel definierte Formular veranschaulicht. Wenn Sie auf das Formular klicken, wird der Ereignishandler aufgerufen.  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>

### <a name="to-generate-an-event-handler-at-run-time-by-using-a-dynamic-method"></a>So generieren Sie anhand einer dynamischen Methode zur Laufzeit einen Ereignishandler  
  
1. Ereignishandlermethoden können mithilfe einfacher dynamischer Methoden und Reflektionsausgabe zur Laufzeit generiert werden. Zum Erstellen eines Ereignishandlers benötigen Sie den Rückgabetyp und die Parametertypen des Delegaten. Diese können über die `Invoke`-Methode des Delegaten abgerufen werden. Im folgenden Code werden diese Informationen über die `GetDelegateReturnType`-Methode und die `GetDelegateParameterTypes`-Methode ermittelt. Den Code für diese Methoden können Sie später in diesem Thema im Abschnitt Beispiel finden.  
  
     Eine <xref:System.Reflection.Emit.DynamicMethod> muss nicht bezeichnet werden, Sie können eine leere Zeichenfolge verwenden. Im folgenden Code wird die dynamische Methode mit dem letzten Argument dem aktuellen Typ zugeordnet. Dadurch erhält der Delegat Zugriff auf alle öffentlichen und privaten Member der `Example`-Klasse.  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2. Generieren Sie einen Methodentext. Diese Methode lädt eine Zeichenfolge, ruft die Überladung der <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>-Methode auf, die eine Zeichenfolge akzeptiert, nimmt den Rückgabewert vom Stapel auf (da der Handler keinen Rückgabetyp aufweist) und wird dann beendet. Weitere Informationen zum Ausgeben dynamischer Methoden finden Sie unter [Vorgehensweise: Definieren und Ausführen von dynamischen Methoden](how-to-define-and-execute-dynamic-methods.md).  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3. Schließen Sie die dynamische Methode ab, indem Sie seine <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>-Methode aufrufen. Fügen Sie den Delegaten mithilfe des `add`-Accessors zur Aufrufliste des Ereignisses hinzu.  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4. Testen Sie das Ereignis. Im folgenden Code wird das im Codebeispiel definierte Formular geladen. Wenn Sie auf das Formular klicken, werden sowohl der vordefinierte als auch der ausgegebene Ereignishandler aufgerufen.  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## <a name="example"></a>Beispiel  

 In den folgenden Codebeispielen wird veranschaulicht, wie eine vorhandene Methode anhand von Reflektion mit einem Ereignis verknüpft wird, und wie eine Methode mithilfe der <xref:System.Reflection.Emit.DynamicMethod>-Klasse zur Laufzeit ausgegeben und mit einem Ereignis verknüpft wird.  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Emit.DynamicMethod>
- <xref:System.Activator.CreateInstance%2A>
- <xref:System.Delegate.CreateDelegate%2A>
- [How to: Definieren und Ausführen von dynamischen Methoden](how-to-define-and-execute-dynamic-methods.md)
- [Reflexion](reflection.md)
