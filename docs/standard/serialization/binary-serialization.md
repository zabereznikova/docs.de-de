---
title: Binäre Serialisierung
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 34ba6cb658a52b647c6fbf9a4161d046f31cd73e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705820"
---
# <a name="binary-serialization"></a>Binäre Serialisierung

Die Serialisierung kann als Prozess der Speicherung eines Objektzustands in einem Speichermedium definiert werden. Im Rahmen dieses Vorgangs werden die öffentlichen und privaten Felder des Objekts und der Name der Klasse, einschließlich der Assembly, die die Klasse enthält, in einen Bytestream umgewandelt, der dann in einen Datenstream geschrieben wird. Wenn das Objekt anschließend deserialisiert wird, wird ein genauer Klon des ursprünglichen Objekts erstellt.

Bei der Implementierung eines Serialisierungsmechanismus in einer objektorientierten Umgebung muss vielfach zwischen einfacher Handhabung und Flexibilät abgewogen werden. Dieser Vorgang lässt sich größtenteils automatisieren, sofern Sie ausreichend Kontrolle über den Vorgang haben. Es kann beispielsweise Situationen geben, in denen eine einfache binäre Serialisierung nicht ausreichend ist, oder aus einem bestimmt Grund kann es erforderlich sein zu entscheiden, welche Felder einer Klasse serialisiert werden müssen. In den folgenden Abschnitten wird der robuste Serialisierungsmechanismus untersucht, der von .NET bereitgestellt wird, und es werden einige wichtige Funktionen hervorgehoben, mit denen Sie diesen Vorgang an Ihre Anforderungen anpassen können.

> [!NOTE]
> Der Zustand eines UTF-8- oder UTF-7-codierten Objektes wird nicht beibehalten, wenn das Objekt mit verschiedenen Versionen von .NET Framework serialisiert und deserialisiert wird.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

Die Art der binären Serialisierung ermöglicht die Änderung der privaten Member innerhalb eines Objekts. Somit wird deren Status geändert. Andere Serialisierungsframeworks wie JSON.NET, die auf der öffentlichen API-Oberfläche ausgeführt werden, werden empfohlen.

## <a name="binary-serialization-in-net-core"></a>Binäre Serialisierung in .NET Core

.NET Core unterstützt binäre Serialisierung mit einer Teilmenge der Typen. Sie finden die Liste der unterstützten Typen im Abschnitt [Serialisierbare Typen](#serializable-types). Der definierte Satz von Typen kann zwischen .NET Framework 4.5.1 und höheren Versionen und .NET Core 2.0 und höheren Versionen serialisiert werden. Andere Implementierungen von .NET, z.B. Mono, werden nicht offiziell unterstützt, sollten jedoch ebenfalls funktionieren.

### <a name="serializable-types"></a>Serialisierbare Typen

- <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.AccessViolationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.AggregateException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ApplicationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ArgumentException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ArgumentNullException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ArithmeticException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Array?displayProperty=nameWithType>
- <xref:System.ArraySegment%601?displayProperty=nameWithType>
- <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Attribute?displayProperty=nameWithType>
- <xref:System.BadImageFormatException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Boolean?displayProperty=nameWithType>
- <xref:System.Byte?displayProperty=nameWithType>
- <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Char?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList?displayProperty=nameWithType>
- <xref:System.Collections.BitArray?displayProperty=nameWithType>
- <xref:System.Collections.Comparer?displayProperty=nameWithType>
- <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType>
- <xref:System.Collections.Hashtable?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.Queue?displayProperty=nameWithType>
- <xref:System.Collections.SortedList?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Stack?displayProperty=nameWithType>
- `System.Collections.Generic.NonRandomizedStringEqualityComparer` (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> (verfügbar in .net Core 2.0.4 und höheren Versionen wird die Serialisierung von .NET Framework zu .net Core nicht unterstützt)
- <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ContextMarshalException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DBNull?displayProperty=nameWithType> (in .net Core 2.0.2 und höheren Versionen verfügbar)
- <xref:System.Data.Common.DbException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.ConstraintException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.DataException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.DataSet?displayProperty=nameWithType>
- <xref:System.Data.DataTable?displayProperty=nameWithType> (es sei denn, Sie legen ' RemotingFormat ' auf ' SerializationFormat. Binary ' fest. in diesem Fall kann es nur mit .net Core 2,1 und höheren Versionen ausgetauscht werden.)
- <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.EvaluateException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.PropertyCollection?displayProperty=nameWithType>
- <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> (verfügbar in .net Core 2.0.4 und höheren Versionen wird die Serialisierung von .NET Framework zu .net Core nicht unterstützt)
- <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.StrongTypingException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DataMisalignedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DateTime?displayProperty=nameWithType>
- <xref:System.DateTimeOffset?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- `System.Diagnostics.Contracts.ContractException` (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DivideByZeroException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.DllNotFoundException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Drawing.Color?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- <xref:System.Drawing.PointF?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- <xref:System.Drawing.RectangleF?displayProperty=nameWithType>
- <xref:System.Drawing.Size?displayProperty=nameWithType>
- <xref:System.Drawing.SizeF?displayProperty=nameWithType>
- <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Enum?displayProperty=nameWithType>
- <xref:System.EventArgs?displayProperty=nameWithType> (in .net Core 2.0.6 und höheren Versionen verfügbar)
- <xref:System.Exception?displayProperty=nameWithType>
- <xref:System.ExecutionEngineException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.FieldAccessException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.FormatException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Globalization.CompareInfo?displayProperty=nameWithType>
- <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Globalization.SortVersion?displayProperty=nameWithType>
- <xref:System.Guid?displayProperty=nameWithType>
- `System.IO.Compression.ZLibException` (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IO.FileFormatException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IO.FileLoadException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IO.IOException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IO.InvalidDataException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IO.PathTooLongException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.InsufficientMemoryException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Int16?displayProperty=nameWithType>
- <xref:System.Int32?displayProperty=nameWithType>
- <xref:System.Int64?displayProperty=nameWithType>
- <xref:System.IntPtr?displayProperty=nameWithType>
- <xref:System.InvalidCastException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.InvalidOperationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.InvalidProgramException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.MemberAccessException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.MethodAccessException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.MissingFieldException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.MissingMemberException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.MissingMethodException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Net.Cookie?displayProperty=nameWithType>
- <xref:System.Net.CookieCollection?displayProperty=nameWithType>
- <xref:System.Net.CookieContainer?displayProperty=nameWithType>
- <xref:System.Net.CookieException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Net.HttpListenerException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Net.WebException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.NotFiniteNumberException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.NotImplementedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.NotSupportedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.NullReferenceException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Numerics.BigInteger?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.ObjectDisposedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.OperationCanceledException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.OutOfMemoryException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.OverflowException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.RankException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> (verfügbar in .net Core 2.0.4 und höheren Versionen wird die Serialisierung von .NET Framework zu .net Core nicht unterstützt)
- <xref:System.Reflection.TargetException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.SByte?displayProperty=nameWithType>
- <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Security.HostProtectionException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Security.SecurityException?displayProperty=nameWithType> (verfügbar in .net Core 2.0.4 und höheren Versionen, eingeschränkte Serialisierungsdaten)
- <xref:System.Security.VerificationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.StackOverflowException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.StringComparer?displayProperty=nameWithType>
- <xref:System.SystemException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Text.StringBuilder?displayProperty=nameWithType>
- <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.TimeSpan?displayProperty=nameWithType>
- <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType>
- <xref:System.TimeZoneInfo?displayProperty=nameWithType>
- <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.TimeoutException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Transactions.TransactionException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Tuple?displayProperty=nameWithType>
- <xref:System.TypeAccessException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.TypeInitializationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.TypeLoadException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.TypeUnloadedException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.UInt16?displayProperty=nameWithType>
- <xref:System.UInt32?displayProperty=nameWithType>
- <xref:System.UInt64?displayProperty=nameWithType>
- <xref:System.UIntPtr?displayProperty=nameWithType>
- <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Uri?displayProperty=nameWithType>
- <xref:System.UriFormatException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.ValueTuple?displayProperty=nameWithType> (nicht serialisierbar in .NET Framework 4,7 und früheren Versionen)
- <xref:System.ValueType?displayProperty=nameWithType>
- <xref:System.Version?displayProperty=nameWithType>
- <xref:System.WeakReference%601?displayProperty=nameWithType>
- <xref:System.WeakReference?displayProperty=nameWithType>
- <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Xml.XmlException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)
- <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> (in .net Core 2.0.4 und höheren Versionen verfügbar)

## <a name="in-this-section"></a>In diesem Abschnitt

- [Konzepte der Serialisierung](../../../docs/standard/serialization/serialization-concepts.md)\
Erläutert zwei Szenarien, in denen die Serialisierung sinnvoll eingesetzt werden kann: wenn Daten im Speicher beibehalten werden sollen und wenn Objekte über Anwendungsdomänen hinweg übergeben werden.

- [Einfache Serialisierung](../../../docs/standard/serialization/basic-serialization.md)\
Beschreibt, wie die Binärdatei und SOAP-Formatierungsprogramme verwendet werden, um Objekte zu serialisieren.

- [Selektive Serialisierung](../../../docs/standard/serialization/selective-serialization.md)\
Beschreibt, wie verhindert wird, dass einige Member einer Klasse serialisiert werden.

- [Benutzerdefinierte Serialisierung](../../../docs/standard/serialization/custom-serialization.md)\
Beschreibt, wie mithilfe der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle die Serialisierung für eine Klasse angepasst wird.

- [Schritte im Serialisierungsprozess](../../../docs/standard/serialization/steps-in-the-serialization-process.md)\
Beschreibt die einzelnen Serialisierungsschritte, die ausgeführt werden, wenn die <xref:System.Runtime.Serialization.Formatter.Serialize%2A>-Methode für ein Formatierungsprogramm aufgerufen wird.

- [Versions tolerante Serialisierung](../../../docs/standard/serialization/version-tolerant-serialization.md)\
Erklärt, wie serialisierbare Typen erstellt werden, die im Lauf der Zeit modifiziert werden können, ohne dass dies zur Folge hat, dass Anwendungen Ausnahmen auslösen.

- \ der [Serialisierungsrichtlinien](../../../docs/standard/serialization/serialization-guidelines.md)
Stellt einige allgemeine Richtlinien zur Entscheidung der Frage bereit, wann ein Objekt serialisiert werden sollte.

## <a name="reference"></a>Referenz

- <xref:System.Runtime.Serialization>\
Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.

## <a name="related-sections"></a>Verwandte Abschnitte

- [XML and SOAP Serialization (XML- und SOAP-Serialisierung)](../../../docs/standard/serialization/xml-and-soap-serialization.md)\
Beschreibt den XML-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.

- [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md)\
Beschreibt Richtlinien für das Schreiben sicheren Codes, die beim Schreiben von befolgt werden sollten, der Serialisierungen durchführt.

- [.NET-Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)) -\
Beschreibt die verschiedenen Kommunikationsverfahren, die in .NET&#160;Framework für die Remotekommunikation zur Verfügung stehen.

- [Mit ASP.net-und XML-Webdienst Clients erstellte XML-Webdienste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))\
Stellt Themen bereit, die beschreiben und erklären, wie mit ASP.NET erstellte XML-Webdienste programmiert werden.
