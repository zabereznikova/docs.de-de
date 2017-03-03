---
title: Implementieren einer Dispose-Methode
description: Implementieren einer Dispose-Methode
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: eca6cdc3-6a14-4296-86fb-1eb2f21455b0
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: c1e06872017eb06c52b5da62b2382398451a13bd
ms.lasthandoff: 01/18/2017

---

# <a name="implementing-a-dispose-method"></a>Implementieren einer Dispose-Methode

Sie implementieren eine [Dispose](xref:System.IDisposable.Dispose)-Methode, um nicht verwaltete Ressourcen freizugeben, die von Ihrer Anwendung verwendet werden. Der .NET-Garbage Collector ordnet nicht verwalteten Arbeitsspeicher weder zu noch gibt er diesen frei. 

Das Muster für das Verwerfen eines Objekts, „Dispose-Muster“ genannt, legt die Ordnung für die Lebensdauer eines Objekts fest. Das Dispose-Muster wird nur für Objekte verwendet, die auf nicht verwaltete Ressourcen zugreifen, wie etwa Datei- und Pipehandles, Registrierungshandles, Wait-Handles oder Zeiger auf Blöcke nicht verwalteten Speichers. Dies liegt daran, dass der Garbage Collector beim Freigeben nicht verwendeter verwalteter Objekte sehr effizient ist, nicht verwaltete Objekt jedoch nicht freigeben kann.

Das Dispose-Muster weist zwei Varianten auf:

* Sie umschließen jede nicht verwaltete Ressource, die ein Typ verwendet, in einem SafeHandle (also in einer von [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) abgeleiteten Klasse). In diesem Fall implementieren Sie die [IDisposable](xref:System.IDisposable)-Schnittstelle und eine zusätzliche `Dispose(Boolean)`-Methode. Dies ist die empfohlene Variante und erfordert kein Überschreiben der [Object.Finalize](xref:System.Object.Finalize)-Methode. 

> [!NOTE]
> Der [Microsoft.Win32.SafeHandles](xref:Microsoft.Win32.SafeHandles)-Namespace stellt einen Satz von Klassen bereit, die von [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) abgeleitet werden und im Abschnitt [Verwenden von SafeHandles](#using-safe-handles) aufgeführt sind. Wenn Sie keine Klasse finden können, die sich zum Freigeben Ihrer nicht verwalteten Ressource eignet, können Sie eine eigene Unterklasse von [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) implementieren. 
 
* Sie implementieren die [IDisposable](xref:System.IDisposable)-Schnittstelle und eine zusätzliche `Dispose(Boolean`)-Methode, und Sie überschreiben auch die [Object.Finalize](xref:System.Object.Finalize)-Methode. Sie müssen [Finalize](xref:System.Object.Finalize) überschreiben, um sicherzustellen, dass nicht verwaltete Ressourcen verworfen werden, wenn die [IDisposable.Dispose](xref:System.IDisposable.Dispose)-Implementierung nicht von einem Consumer Ihres Typs aufgerufen wird. Wenn Sie das unter dem vorherigen Aufzählungspunkt beschriebene empfohlene Verfahren anwenden, führt die [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)-Klasse dies für Sie durch. 

Um sicherzustellen, dass Ressourcen immer entsprechend bereinigt werden, sollte eine [Dispose](xref:System.IDisposable.Dispose)-Methode mehrmals aufgerufen werden können, ohne eine Ausnahme auszulösen. 

Das Codebeispiel für die [GC.KeepAlive](xref:System.GC.KeepAlive(System.Object))-Methode veranschaulicht, wie eine aggressive Garbage Collection die Ausführung eines Finalizers bewirken kann, während ein Member des freigegebenen Objekts noch ausgeführt wird. Es empfiehlt sich, am Ende einer `Dispose`-Methode mit langer Ausführungsdauer die [KeepAlive](xref:System.GC.KeepAlive(System.Object))-Methode aufzurufen.

## <a name="dispose-and-disposeboolean"></a>Dispose() und Dispose(Boolean)

Die [IDisposable](xref:System.IDisposable)-Schnittstelle erfordert die Implementierung einer einzelnen parameterlosen Methode, [Dispose](xref:System.IDisposable.Dispose). Für das Dispose-Muster müssen jedoch zwei `Dispose`-Methoden implementiert werden: 

* Eine öffentliche, nicht virtuelle (`NonInheritable` in Visual Basic) [IDisposable.Dispose](xref:System.IDisposable.Dispose)-Implementierung, die keine Parameter aufweist.

* Eine geschützte, virtuelle (`Overridable` in Visual Basic) `Dispose`-Methode mit der folgenden Signatur:

  ```cs
  protected virtual void Dispose(bool disposing)
  ```

  ```vb
  Protected Overridable Sub Dispose(disposing As Boolean)
  ```

### <a name="the-dispose-overload"></a>Die Dispose() Überladung

Da die öffentliche, nicht virtuelle (`NonInheritable` in Visual Basic), parameterlose `Dispose`-Methode von einem Consumer des Typs aufgerufen wird, besteht ihr Zweck darin, nicht verwaltete Ressourcen freizugeben und anzugeben, dass der Finalizer, sofern vorhanden, nicht ausgeführt werden muss. Daher weist sie eine Standardimplementierung auf:

```cs
public void Dispose()
{
   // Dispose of unmanaged resources.
   Dispose(true);
   // Suppress finalization.
   GC.SuppressFinalize(this);
}
```

```vb
Public Sub Dispose() _
           Implements IDisposable.Dispose
   ' Dispose of unmanaged resources.
   Dispose(True)
   ' Suppress finalization.
   GC.SuppressFinalize(Me)
End Sub
```

Die `Dispose`-Methode führt die Bereinigung aller Objekte aus, damit der Garbage Collector nicht mehr die [Object.Finalize](xref:System.Object.Finalize)-Überschreibung der Objekte aufrufen muss. Daher verhindert der Aufruf der [GC.SuppressFinalize](xref:System.GC.SuppressFinalize(System.Object))-Methode, dass der Garbage Collector den Finalizer ausführt. Wenn der Typ keinen Finalizer aufweist, bleibt der Aufruf von [SuppressFinalize](xref:System.GC.SuppressFinalize(System.Object)) ohne Auswirkungen. Beachten Sie, dass die tatsächliche Arbeit des Freigebens nicht verwalteter Ressourcen durch die zweite Überladung der `Dispose`-Methode ausgeführt wird.

### <a name="the-disposeboolean-overload"></a>Die Dispose(Boolean) Überladung

In der zweiten Überladung ist der *disposing*-Parameter ein [Boolean](xref:System.Boolean)-Wert, der angibt, ob der Methodenaufruf von einer [Dispose](xref:System.IDisposable.Dispose)-Methode (der Wert ist `true`) oder von einem Finalizer (der Wert ist `false`) stammt. 

Der Text der Methode besteht aus zwei Codeblöcken: 

* Ein Block, der nicht verwaltete Ressourcen freigibt. Dieser Block wird unabhängig vom Wert des *disposing*-Parameters ausgeführt. 

* Ein bedingter Block, der verwaltete Ressourcen freigibt. Dieser Block wird ausgeführt, wenn der Wert von *disposing* gleich `true` ist. Die verwalteten Ressourcen, die freigegeben werden, können Folgendes umfassen: 

    **Verwaltete Objekte, die IDisposable implementieren**. Der bedingte Block kann verwendet werden, um deren [Dispose](xref:System.IDisposable.Dispose)-Implementierung aufzurufen. Wenn Sie ein SafeHandle verwendet haben, um die nicht verwaltete Ressource einschließen, sollten Sie die [SafeHandle.Dispose(Boolean](xref:System.Runtime.InteropServices.SafeHandle.Dispose(System.Boolean))-Implementierung hier aufrufen. 

    **Verwaltete Objekte, die viel Arbeitsspeicher belegen oder knappe Ressourcen nutzen.** Durch die explizite Freigabe in der `Dispose`-Methode werden diese Objekte schneller freigegeben, als wenn sie vom Garbage Collector nicht deterministisch freigegeben werden würden. 


Wenn der Methodenaufruf von einem Finalizer stammt (das heißt, *disposing* ist `false`), wird nur der Code ausgeführt, der nicht verwaltete Ressourcen freigibt. Die Reihenfolge, in der der Garbage Collector verwaltete Objekte während des Abschlusses zerstört, ist nicht definiert. Durch Aufrufen dieser `Dispose`-Überladung mit dem Wert `false` wird daher verhindert, dass der Finalizer versucht, verwaltete Ressourcen freizugeben, die möglicherweise bereits freigegeben wurden. 

## <a name="implementing-the-dispose-pattern-for-a-base-class"></a>Implementieren des Dispose-Musters für eine Basisklasse

Wenn Sie das Dispose-Muster für eine Basisklasse implementieren, müssen Sie Folgendes bereitstellen: 

> [!IMPORTANT]
> Sie sollten dieses Muster für alle Basisklassen implementieren, die [IDisposable](xref:System.IDisposable) implementieren und nicht `sealed` sind. 
 
* Eine [Dispose](xref:System.IDisposable.Dispose)-Implementierung, die die `Dispose(Boolean)`-Methode aufruft. 

* Eine `Dispose(Boolean)`-Methode, die die eigentliche Arbeit des Freigebens von Ressourcen ausführt. 

* Entweder eine von [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) abgeleitete Klasse, die die nicht verwaltete Ressource einschließt (empfohlen), oder eine Überschreibung der [Object.Finalize](xref:System.Object.Finalize)-Methode. Die [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)-Klasse stellt einen Finalizer bereit, sodass Sie keinen programmieren müssen. 

Im Folgenden finden Sie das allgemeine Muster für die Implementierung des Dispose-Musters für eine Basisklasse, die ein SafeHandle verwendet. 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.Runtime.InteropServices;

class BaseClass : IDisposable
{
   // Flag: Has Dispose already been called?
   bool disposed = false;
   // Instantiate a SafeHandle instance.
   SafeHandle handle = new SafeFileHandle(IntPtr.Zero, true);

   // Public implementation of Dispose pattern callable by consumers.
   public void Dispose()
   { 
      Dispose(true);
      GC.SuppressFinalize(this);           
   }

   // Protected implementation of Dispose pattern.
   protected virtual void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         handle.Dispose();
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //
      disposed = true;
   }
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.Runtime.InteropServices

Class BaseClass : Implements IDisposable
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False
   ' Instantiate a SafeHandle instance.
   Dim handle As SafeHandle = New SafeFileHandle(IntPtr.Zero, True)

   ' Public implementation of Dispose pattern callable by consumers.
   Public Sub Dispose() _
              Implements IDisposable.Dispose
      Dispose(True)
      GC.SuppressFinalize(Me)           
   End Sub

   ' Protected implementation of Dispose pattern.
   Protected Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         handle.Dispose()
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True
   End Sub
End Class
```

> [!NOTE] 
> Im vorherigen Beispiel wird ein [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle)-Objekt zum Veranschaulichen des Musters verwendet. Stattdessen kann auch ein beliebiges anderes von [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) abgeleitetes Objekt verwendet werden. Beachten Sie, dass im Beispiel das [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle)-Objekt nicht ordnungsgemäß instanziiert wird. 
 
Im Folgenden finden Sie das allgemeine Muster für die Implementierung des Dispose-Musters für eine Basisklasse, die [Object.Finalize](xref:System.Object.Finalize) überschreibt. 

```cs
using System;

class BaseClass : IDisposable
{
   // Flag: Has Dispose already been called?
   bool disposed = false;

   // Public implementation of Dispose pattern callable by consumers.
   public void Dispose()
   { 
      Dispose(true);
      GC.SuppressFinalize(this);           
   }

   // Protected implementation of Dispose pattern.
   protected virtual void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //
      disposed = true;
   }

   ~BaseClass()
   {
      Dispose(false);
   }
}
```

```vb
Class BaseClass : Implements IDisposable
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False

   ' Public implementation of Dispose pattern callable by consumers.
   Public Sub Dispose() _
              Implements IDisposable.Dispose
      Dispose(True)
      GC.SuppressFinalize(Me)           
   End Sub

   ' Protected implementation of Dispose pattern.
   Protected Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True
   End Sub

   Protected Overrides Sub Finalize()
      Dispose(False)      
   End Sub
End Class
```

> [!NOTE]
> In C# überschreiben Sie [Object.Finalize](xref:System.Object.Finalize), indem Sie einen `destructor` definieren. 


## <a name="implementing-the-dispose-pattern-for-a-derived-class"></a>Implementieren des Dispose-Musters für eine abgeleitete Klasse

Eine Klasse, die von einer Klasse abgeleitet ist, die die [IDisposable](xref:System.IDisposable)-Schnittstelle implementiert, sollte [IDisposable](xref:System.IDisposable) nicht implementieren, da die Basisklassenimplementierung von [IDisposable.Dispose](xref:System.IDisposable.Dispose) von den abgeleiteten Klassen geerbt wird. Stattdessen müssen Sie Folgendes bereitstellen, um das Dispose-Muster für eine abgeleitete Klasse zu implementieren: 

* Eine `protected Dispose(Boolean)`-Methode, die die Basisklassenmethode überschreibt und die eigentliche Freigabe der Ressourcen der abgeleiteten Klasse durchführt. Diese Methode sollte auch die `Dispose(Boolean)`-Methode der Basisklasse aufrufen und ihr den Wert `true` für das *disposing*-Argument übergeben. 

* Entweder eine von [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) abgeleitete Klasse, die die nicht verwaltete Ressource einschließt (empfohlen), oder eine Überschreibung der [Object.Finalize](xref:System.Object.Finalize)-Methode. Die [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)-Klasse stellt einen Finalizer bereit, sodass Sie keinen programmieren müssen. Wenn Sie einen Finalizer bereitstellen, sollte er die `Dispose(Boolean)`-Überladung mit einem *disposing*-Argument mit dem Wert `false` aufrufen. 

Im Folgenden finden Sie das allgemeine Muster für das Implementieren des Dispose-Musters für eine abgeleitete Klasse, die ein SafeHandle verwendet: 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.Runtime.InteropServices;

class DerivedClass : BaseClass
{
   // Flag: Has Dispose already been called?
   bool disposed = false;
   // Instantiate a SafeHandle instance.
   SafeHandle handle = new SafeFileHandle(IntPtr.Zero, true);

   // Protected implementation of Dispose pattern.
   protected override void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         handle.Dispose();
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //

      disposed = true;
      // Call base class implementation.
      base.Dispose(disposing);
   }
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.Runtime.InteropServices

Class DerivedClass : Inherits BaseClass 
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False
   ' Instantiate a SafeHandle instance.
   Dim handle As SafeHandle = New SafeFileHandle(IntPtr.Zero, True)

   ' Protected implementation of Dispose pattern.
   Protected Overrides Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         handle.Dispose()
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True

      ' Call base class implementation.
      MyBase.Dispose(disposing)
   End Sub
End Class
```

> [!NOTE] 
> Im vorherigen Beispiel wird ein [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle)-Objekt zum Veranschaulichen des Musters verwendet. Stattdessen kann auch ein beliebiges anderes von [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) abgeleitetes Objekt verwendet werden. Beachten Sie, dass im Beispiel das [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle)-Objekt nicht ordnungsgemäß instanziiert wird. 

Im Folgenden finden Sie das allgemeine Muster für die Implementierung des Dispose-Musters für eine abgeleitete Klasse, die [Object.Finalize](xref:System.Object.Finalize) überschreibt:

```cs
using System;

class DerivedClass : BaseClass
{
   // Flag: Has Dispose already been called?
   bool disposed = false;

   // Protected implementation of Dispose pattern.
   protected override void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //
      disposed = true;

      // Call the base class implementation.
      base.Dispose(disposing);
   }

   ~DerivedClass()
   {
      Dispose(false);
   }
}
```

```vb
Class DerivedClass : Inherits BaseClass
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False

   ' Protected implementation of Dispose pattern.
   Protected Overrides Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True

      ' Call the base class implementation.
      MyBase.Dispose(disposing)
   End Sub

   Protected Overrides Sub Finalize()
      Dispose(False)
   End Sub 
End Class
```

> [!NOTE]
> In C# überschreiben Sie [Object.Finalize](xref:System.Object.Finalize), indem Sie einen `destructor` definieren.

## <a name="using-safe-handles"></a>Verwenden von SafeHandles

Das Schreiben von Code für den Finalizer eines Objekts ist eine komplexe Aufgabe, die Probleme verursachen kann, wenn sie nicht ordnungsgemäß gelöst wird. Daher wird empfohlen, [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)-Objekte zu erstellen, anstatt einen Finalizer zu implementieren.

Von der [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)-Klasse abgeleitete Klassen vereinfachen Probleme mit der Objektlebensdauer, indem sie Handles ohne Unterbrechung zuweisen und freigeben. Sie enthalten einen kritischen Finalizer, der auf jeden Fall ausgeführt wird, während eine Anwendungsdomäne entladen wird. Die folgenden abgeleiteten Klassen im [Microsoft.Win32.SafeHandles](xref:Microsoft.Win32.SafeHandles)-Namespace stellen SafeHandles bereit: 

* Die Klassen [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle), [SafeMemoryMappedFileHandle](xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle) und [SafePipeHandle](xref:Microsoft.Win32.SafeHandles.SafePipeHandle) für Dateien, dem Arbeitsspeicher zugeordnete Dateien und Pipes. 

* Die [SafeMemoryMappedViewHandle](xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle)-Klasse für Speicheransichten. 

* Die Klassen [SafeNCryptKeyHandle](https://msdn.microsoft.com/library/microsoft.win32.safehandles.safencryptkeyhandle(v=vs.110).aspx), [SafeNCryptProviderHandle](https://msdn.microsoft.com/library/microsoft.win32.safehandles.safencryptproviderhandle(v=vs.110).aspx) und [SafeNCryptSecretHandle](https://msdn.microsoft.com/library/microsoft.win32.safehandles.safencryptsecrethandle(v=vs.110).aspx) für Kryptografiekonstrukte.

* Die [SafeRegistryHandle](xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle)-Klasse für Registrierungsschlüssel. 

* Die [SafeWaitHandle](xref:Microsoft.Win32.SafeHandles.SafeWaitHandle)-Klasse für Wait-Handles. 

## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-base-class"></a>Verwenden eines SafeHandles zum Implementieren des Dispose-Musters für eine Basisklasse

Das folgende Beispiel zeigt das Dispose-Muster für eine Basisklasse, `DisposableStreamResource`, die ein SafeHandle verwendet, um nicht verwaltete Ressourcen zu kapseln. Es definiert eine `DisposableResource`-Klasse, die ein [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle) verwendet, um ein [Stream](xref:System.IO.Stream)-Objekt zu umschließen, das eine offene Datei darstellt. Die `DisposableResource`-Methode enthält auch eine einzelne Eigenschaft, `Size`, die die Gesamtzahl von Bytes im Dateistream zurückgibt. 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.IO;
using System.Runtime.InteropServices;

public class DisposableStreamResource : IDisposable
{
   // Define constants.
   protected const uint GENERIC_READ = 0x80000000;
   protected const uint FILE_SHARE_READ = 0x00000001;
   protected const uint OPEN_EXISTING = 3;
   protected const uint FILE_ATTRIBUTE_NORMAL = 0x80;
   protected IntPtr INVALID_HANDLE_VALUE = new IntPtr(-1);
   private const int INVALID_FILE_SIZE = unchecked((int) 0xFFFFFFFF);

   // Define Windows APIs.
   [DllImport("kernel32.dll", EntryPoint = "CreateFileW", CharSet = CharSet.Unicode)]
   protected static extern IntPtr CreateFile (
                                  string lpFileName, uint dwDesiredAccess, 
                                  uint dwShareMode, IntPtr lpSecurityAttributes, 
                                  uint dwCreationDisposition, uint dwFlagsAndAttributes, 
                                  IntPtr hTemplateFile);

   [DllImport("kernel32.dll")]
   private static extern int GetFileSize(SafeFileHandle hFile, out int lpFileSizeHigh);

   // Define locals.
   private bool disposed = false;
   private SafeFileHandle safeHandle; 
   private long bufferSize;
   private int upperWord;

   public DisposableStreamResource(string filename)
   {
      if (filename == null)
         throw new ArgumentNullException("The filename cannot be null.");
      else if (filename == "")
         throw new ArgumentException("The filename cannot be an empty string.");

      IntPtr handle = CreateFile(filename, GENERIC_READ, FILE_SHARE_READ,
                                 IntPtr.Zero, OPEN_EXISTING, FILE_ATTRIBUTE_NORMAL,
                                 IntPtr.Zero);
      if (handle != INVALID_HANDLE_VALUE)
         safeHandle = new SafeFileHandle(handle, true);
      else
         throw new FileNotFoundException(String.Format("Cannot open '{0}'", filename));

      // Get file size.
      bufferSize = GetFileSize(safeHandle, out upperWord); 
      if (bufferSize == INVALID_FILE_SIZE)
         bufferSize = -1;
      else if (upperWord > 0) 
         bufferSize = (((long)upperWord) << 32) + bufferSize;
   }

   public long Size 
   { get { return bufferSize; } }

   public void Dispose()
   {
      Dispose(true);
      GC.SuppressFinalize(this);
   }           

   protected virtual void Dispose(bool disposing)
   {
      if (disposed) return;

      // Dispose of managed resources here.
      if (disposing)
         safeHandle.Dispose();

      // Dispose of any unmanaged resources not wrapped in safe handles.

      disposed = true;
   }  
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.IO

Public Class DisposableStreamResource : Implements IDisposable
   ' Define constants.
   Protected Const GENERIC_READ As UInteger = &H80000000ui
   Protected Const FILE_SHARE_READ As UInteger = &H0000000i
   Protected Const OPEN_EXISTING As UInteger = 3
   Protected Const FILE_ATTRIBUTE_NORMAL As UInteger = &H80
   Protected INVALID_HANDLE_VALUE As New IntPtr(-1)
   Private Const INVALID_FILE_SIZE As Integer = &HFFFFFFFF

   ' Define Windows APIs.
   Protected Declare Function CreateFile Lib "kernel32" Alias "CreateFileA" (
                                         lpFileName As String, dwDesiredAccess As UInt32, 
                                         dwShareMode As UInt32, lpSecurityAttributes As IntPtr, 
                                         dwCreationDisposition As UInt32, dwFlagsAndAttributes As UInt32, 
                                         hTemplateFile As IntPtr) As IntPtr
   Private Declare Function GetFileSize Lib "kernel32" (hFile As SafeFileHandle, 
                                                        ByRef lpFileSizeHigh As Integer) As Integer

   ' Define locals.
   Private disposed As Boolean = False
   Private safeHandle As SafeFileHandle 
   Private bufferSize As Long 
   Private upperWord As Integer

   Public Sub New(filename As String)
      If filename Is Nothing Then
         Throw New ArgumentNullException("The filename cannot be null.")
      Else If filename = ""
         Throw New ArgumentException("The filename cannot be an empty string.")
      End If

      Dim handle As IntPtr = CreateFile(filename, GENERIC_READ, FILE_SHARE_READ,
                                        IntPtr.Zero, OPEN_EXISTING, FILE_ATTRIBUTE_NORMAL,
                                        IntPtr.Zero)
      If handle <> INVALID_HANDLE_VALUE Then
         safeHandle = New SafeFileHandle(handle, True)
      Else
         Throw New FileNotFoundException(String.Format("Cannot open '{0}'", filename))
      End If

      ' Get file size.
      bufferSize = GetFileSize(safeHandle, upperWord) 
      If bufferSize = INVALID_FILE_SIZE Then
         bufferSize = -1
      Else If upperWord > 0 Then 
         bufferSize = (CLng(upperWord) << 32) + bufferSize
      End If     
   End Sub

   Public ReadOnly Property Size As Long
      Get
         Return bufferSize
      End Get
   End Property

   Public Sub Dispose() _
              Implements IDisposable.Dispose
      Dispose(True)
      GC.SuppressFinalize(Me)
   End Sub           

   Protected Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Exit Sub

      ' Dispose of managed resources here.
      If disposing Then
         safeHandle.Dispose()
      End If

      ' Dispose of any unmanaged resources not wrapped in safe handles.

      disposed = True
   End Sub  
End Class
```

## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-derived-class"></a>Verwenden eines SafeHandles zum Implementieren des Dispose-Musters für eine abgeleitete Klasse

Das folgende Beispiel zeigt das Dispose-Muster für eine abgeleitete Klasse, `DisposableStreamResource2`, die von der `DisposableStreamResource`-Klasse erbt, die im vorherigen Beispiel dargestellt wurde. Die Klasse fügt eine zusätzliche Methode, `WriteFileInfo`, hinzu und verwendet ein [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle)-Objekt, um das Handle der beschreibbaren Datei zu umschließen. 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.IO;
using System.Runtime.InteropServices;
using System.Threading;

public class DisposableStreamResource2 : DisposableStreamResource
{
   // Define additional constants.
   protected const uint GENERIC_WRITE = 0x40000000; 
   protected const uint OPEN_ALWAYS = 4;

   // Define additional APIs.
   [DllImport("kernel32.dll")]   
   protected static extern bool WriteFile(
                                SafeFileHandle safeHandle, string lpBuffer, 
                                int nNumberOfBytesToWrite, out int lpNumberOfBytesWritten,
                                IntPtr lpOverlapped);

   // Define locals.
   private bool disposed = false;
   private string filename;
   private bool created = false;
   private SafeFileHandle safeHandle;

   public DisposableStreamResource2(string filename) : base(filename)
   {
      this.filename = filename;
   }

   public void WriteFileInfo()
   { 
      if (! created) {
         IntPtr hFile = CreateFile(xref:".\FileInfo.txt", GENERIC_WRITE, 0, 
                                   IntPtr.Zero, OPEN_ALWAYS, 
                                   FILE_ATTRIBUTE_NORMAL, IntPtr.Zero);
         if (hFile != INVALID_HANDLE_VALUE)
            safeHandle = new SafeFileHandle(hFile, true);
         else
            throw new IOException("Unable to create output file.");

         created = true;
      }

      string output = String.Format("{0}: {1:N0} bytes\n", filename, Size);
      int bytesWritten;
      bool result = WriteFile(safeHandle, output, output.Length, out bytesWritten, IntPtr.Zero);                                     
   }

   protected new virtual void Dispose(bool disposing)
   {
      if (disposed) return;

      // Release any managed resources here.
      if (disposing)
         safeHandle.Dispose();

      disposed = true;

      // Release any unmanaged resources not wrapped by safe handles here.

      // Call the base class implementation.
      base.Dispose(true);
   }
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.IO

Public Class DisposableStreamResource2 : Inherits DisposableStreamResource
   ' Define additional constants.
   Protected Const GENERIC_WRITE As Integer = &H40000000 
   Protected Const OPEN_ALWAYS As Integer = 4

   ' Define additional APIs.
   Protected Declare Function WriteFile Lib "kernel32.dll" (
                              safeHandle As SafeFileHandle, lpBuffer As String, 
                              nNumberOfBytesToWrite As Integer, ByRef lpNumberOfBytesWritten As Integer,
                              lpOverlapped As Object) As Boolean

   ' Define locals.
   Private disposed As Boolean = False
   Private filename As String
   Private created As Boolean = False
   Private safeHandle As SafeFileHandle

   Public Sub New(filename As String)
      MyBase.New(filename)
      Me.filename = filename
   End Sub

   Public Sub WriteFileInfo() 
      If Not created Then
         Dim hFile As IntPtr = CreateFile(".\FileInfo.txt", GENERIC_WRITE, 0, 
                                          IntPtr.Zero, OPEN_ALWAYS, 
                                          FILE_ATTRIBUTE_NORMAL, IntPtr.Zero)
         If hFile <> INVALID_HANDLE_VALUE Then
            safeHandle = New SafeFileHandle(hFile, True)
         Else
            Throw New IOException("Unable to create output file.")
         End If
         created = True
      End If
      Dim output As String = String.Format("{0}: {1:N0} bytes {2}", filename, Size, 
                                           vbCrLf)
      WriteFile(safeHandle, output, output.Length, 0&, Nothing)                                     
   End Sub

   Protected Overloads Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Exit Sub

      ' Release any managed resources here.
      If disposing Then
         safeHandle.Dispose()
      End If

      disposed = True
      ' Release any unmanaged resources not wrapped by safe handles here.

      ' Call the base class implementation.
      MyBase.Dispose(True)
   End Sub
End Class
```

## <a name="see-also"></a>Siehe auch

[SuppressFinalize](xref:System.GC.SuppressFinalize(System.Object))

[IDisposable](xref:System.IDisposable)

[IDisposable.Dispose](xref:System.IDisposable.Dispose)

[Microsoft.Win32.SafeHandles](xref:Microsoft.Win32.SafeHandles)

[System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)

[IDisposable.Dispose](xref:System.IDisposable.Dispose)

