---
title: Nicht unterstützte APIs in .NET Core
titleSuffix: ''
description: Erfahren Sie, welche APIs aus .NET Framework immer eine Ausnahme in .NET Core auslösen.
ms.date: 12/23/2019
ms.openlocfilehash: c4b94321d30cacd90d5c2ee23c258681683a6faa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77092966"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a>APIs, die in .NET Core immer Ausnahmen auslösen

Die folgenden APIs lösen für .NET Core auf allen oder einer Teilmenge aller Plattformen immer die Ausnahme <xref:System.PlatformNotSupportedException> aus.

In diesem Artikel werden die betroffenen API-Member nach Namespace organisiert.

> [!NOTE]
>
> - Dies ist nicht die endgültige Fassung dieses Artikels. Er enthält keine vollständige Liste der APIs, die Ausnahmen in .NET Core auslösen.
> - In diesem Artikel sind die expliziten Schnittstellenimplementierungen für die binäre Serialisierung, die in .NET Core eine Ausnahme auslösen, nicht enthalten. Weitere Informationen finden Sie unter [Binäre Serialisierung](../../standard/serialization/binary-serialization.md#net-core).

## <a name="system"></a>System

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | Alle |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | Alle |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | Alle |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | Alle |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | Alle |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | Alle |

## <a name="systemcodedomcompiler"></a>System.CodeDom.Compiler

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | Alle |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | Alle |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | Alle |

## <a name="systemcollectionsspecialized"></a>System.Collections.Specialized

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | Alle |

## <a name="systemconfiguration"></a>System.Configuration

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (alle Member) | Alle |

## <a name="systemconsole"></a>System.Console

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Console.BufferHeight?displayProperty=nameWithType> (nur „set“) | Linux und macOS |
| <xref:System.Console.BufferWidth?displayProperty=nameWithType> (nur „set“) | Linux und macOS |
| <xref:System.Console.CursorSize?displayProperty=nameWithType> (nur „set“) | Linux und macOS |
| <xref:System.Console.CursorVisible?displayProperty=nameWithType> (nur „get“) | Linux und macOS |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Console.Title?displayProperty=nameWithType> (nur „get“) | Linux und macOS |
| <xref:System.Console.WindowHeight?displayProperty=nameWithType> (nur „set“) | Linux und macOS |
| <xref:System.Console.WindowLeft?displayProperty=nameWithType> (nur „set“) | Linux und macOS |
| <xref:System.Console.WindowTop?displayProperty=nameWithType> (nur „set“) | Linux und macOS |
| <xref:System.Console.WindowWidth?displayProperty=nameWithType> (nur „set“) | Linux und macOS |

## <a name="systemdatacommon"></a>System.Data.Common

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (löst <xref:System.NotSupportedException> aus) | Alle |

## <a name="systemdiagnosticsprocess"></a>System.Diagnostics.Process

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (nur „set“) | Linux |
| <xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (nur „set“) | Linux |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | macOS |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (nur „set“) | Linux und macOS |
| <xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (nur „get“) | macOS |
| <xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (nur „set“) | Linux und macOS |

## <a name="systemio"></a>System.IO

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |

## <a name="systemiopipes"></a>System.IO.Pipes

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (nur „set“) | Linux und macOS |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | Linux und macOS |

## <a name="systemmedia"></a>System. Media

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |

## <a name="systemnet"></a>System.Net

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | Alle |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | Alle |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |

## <a name="systemnetnetworkinformation"></a>System.Net.NetworkInformation

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | Windows (UWP) |

## <a name="systemnetsockets"></a>System.Net.Sockets

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)?displayProperty=nameWithType> | Alle |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | Alle |

## <a name="systemnetwebsockets"></a>System.Net.WebSockets

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | Alle |

## <a name="systemreflection"></a>System.Reflection

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | Alle |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | Alle |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | Alle |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | Alle |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | Alle |

## <a name="systemruntimecompilerservices"></a>System.Runtime.CompilerServices

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | Alle |

## <a name="systemruntimeinteropservices"></a>System.Runtime.InteropServices

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | Alle |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | Alle |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | Alle |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | Alle |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | Linux und macOS |

## <a name="systemruntimeserialization"></a>System.Runtime.Serialization

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | Alle |

## <a name="systemsecurity"></a>System.Security

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | Alle |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | Alle |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | Alle |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | Alle |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | Alle |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | Alle |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | Alle |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | Alle |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | Alle |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | Alle |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | Alle |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | Alle |

## <a name="systemsecurityclaims"></a>System.Security.Claims

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |

## <a name="systemsecuritycryptography"></a>System.Security.Cryptography

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | Linux und macOS |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | Alle |

## <a name="systemsecuritycryptographypkcs"></a>System.Security.Cryptography.Pkcs

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | Alle |

## <a name="systemsecuritycryptographyx509certificates"></a>System.Security.Cryptography.X509Certificates

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (nur „set“) | Alle |

## <a name="systemsecurityauthenticationextendedprotection"></a>System.Security.Authentication.ExtendedProtection

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |

## <a name="systemsecuritypolicy"></a>System.Security.Policy

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |

## <a name="systemserviceprocessservicecontroller"></a>System.ServiceProcess.ServiceController

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |

## <a name="systemtextregularexpressions"></a>System.Text.RegularExpressions

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | Alle |

## <a name="systemthreading"></a>System.Threading

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Alle |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | Alle |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | Alle |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | Alle |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | Alle |

## <a name="systemxml"></a>System.Xml

| Member | Plattformen, auf denen eine Ausnahme ausgelöst wird |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | Alle |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | Alle |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | Alle |

## <a name="see-also"></a>Weitere Informationen

- [Breaking Changes für die Migration von .NET Framework 3.0 zu .NET Core](../compatibility/fx-core.md)
- [Binäre Serialisierung in .NET Core](../../standard/serialization/binary-serialization.md#net-core)
- [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md)
