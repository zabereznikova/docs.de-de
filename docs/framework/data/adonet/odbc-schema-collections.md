---
title: ODBC-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: 36d0859b897bfcea33803c219ade14722ed90421
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766646"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="8b84d-102">ODBC-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="8b84d-102">ODBC Schema Collections</span></span>
<span data-ttu-id="8b84d-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Treiber für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="8b84d-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="8b84d-104">Microsoft SQL Server-ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="8b84d-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="8b84d-105">Der Microsoft SQL Server-ODBC-Treiber unterstützt die folgenden spezifischen schemaauflistungen zusätzlich zu den allgemeinen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="8b84d-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="8b84d-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="8b84d-106">Tables</span></span>  
  
-   <span data-ttu-id="8b84d-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="8b84d-107">Indexes</span></span>  
  
-   <span data-ttu-id="8b84d-108">Columns</span><span class="sxs-lookup"><span data-stu-id="8b84d-108">Columns</span></span>  
  
-   <span data-ttu-id="8b84d-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="8b84d-109">Procedures</span></span>  
  
-   <span data-ttu-id="8b84d-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8b84d-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="8b84d-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8b84d-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="8b84d-112">Ansichten</span><span class="sxs-lookup"><span data-stu-id="8b84d-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="8b84d-113">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="8b84d-113">Tables and Views</span></span>  
  
|<span data-ttu-id="8b84d-114">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-114">ColumnName</span></span>|<span data-ttu-id="8b84d-115">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="8b84d-116">TABLE_CAT</span></span>|<span data-ttu-id="8b84d-117">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-117">String</span></span>|  
|<span data-ttu-id="8b84d-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8b84d-118">TABLE_SCHEM</span></span>|<span data-ttu-id="8b84d-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-119">String</span></span>|  
|<span data-ttu-id="8b84d-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-120">TABLE_NAME</span></span>|<span data-ttu-id="8b84d-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-121">String</span></span>|  
|<span data-ttu-id="8b84d-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-122">TABLE_TYPE</span></span>|<span data-ttu-id="8b84d-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-123">String</span></span>|  
|<span data-ttu-id="8b84d-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-124">REMARKS</span></span>|<span data-ttu-id="8b84d-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="8b84d-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="8b84d-126">Indexes</span></span>  
  
|<span data-ttu-id="8b84d-127">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-127">ColumnName</span></span>|<span data-ttu-id="8b84d-128">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="8b84d-129">TABLE_CAT</span></span>|<span data-ttu-id="8b84d-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-130">String</span></span>|  
|<span data-ttu-id="8b84d-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8b84d-131">TABLE_SCHEM</span></span>|<span data-ttu-id="8b84d-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-132">String</span></span>|  
|<span data-ttu-id="8b84d-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-133">TABLE_NAME</span></span>|<span data-ttu-id="8b84d-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-134">String</span></span>|  
|<span data-ttu-id="8b84d-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="8b84d-135">NON_UNIQUE</span></span>|<span data-ttu-id="8b84d-136">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-136">Int16</span></span>|  
|<span data-ttu-id="8b84d-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8b84d-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="8b84d-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-138">String</span></span>|  
|<span data-ttu-id="8b84d-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-139">INDEX_NAME</span></span>|<span data-ttu-id="8b84d-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-140">String</span></span>|  
|<span data-ttu-id="8b84d-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-141">TYPE</span></span>|<span data-ttu-id="8b84d-142">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-142">Int16</span></span>|  
|<span data-ttu-id="8b84d-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8b84d-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="8b84d-144">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-144">Int16</span></span>|  
|<span data-ttu-id="8b84d-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-145">COLUMN_NAME</span></span>|<span data-ttu-id="8b84d-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-146">String</span></span>|  
|<span data-ttu-id="8b84d-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="8b84d-147">ASC_OR_DESC</span></span>|<span data-ttu-id="8b84d-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-148">String</span></span>|  
|<span data-ttu-id="8b84d-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="8b84d-149">CARDINATLITY</span></span>|<span data-ttu-id="8b84d-150">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-150">Int32</span></span>|  
|<span data-ttu-id="8b84d-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="8b84d-151">PAGES</span></span>|<span data-ttu-id="8b84d-152">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-152">Int32</span></span>|  
|<span data-ttu-id="8b84d-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="8b84d-153">FILTER_CONDITION</span></span>|<span data-ttu-id="8b84d-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-154">String</span></span>|  
|<span data-ttu-id="8b84d-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8b84d-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="8b84d-156">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-156">String</span></span>|  
|<span data-ttu-id="8b84d-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="8b84d-158">Byte</span><span class="sxs-lookup"><span data-stu-id="8b84d-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="8b84d-159">Columns</span><span class="sxs-lookup"><span data-stu-id="8b84d-159">Columns</span></span>  
  
|<span data-ttu-id="8b84d-160">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-160">ColumnName</span></span>|<span data-ttu-id="8b84d-161">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="8b84d-162">TABLE_CAT</span></span>|<span data-ttu-id="8b84d-163">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-163">String</span></span>|  
|<span data-ttu-id="8b84d-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8b84d-164">TABLE_SCHEM</span></span>|<span data-ttu-id="8b84d-165">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-165">String</span></span>|  
|<span data-ttu-id="8b84d-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-166">TABLE_NAME</span></span>|<span data-ttu-id="8b84d-167">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-167">String</span></span>|  
|<span data-ttu-id="8b84d-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-168">COLUMN_NAME</span></span>|<span data-ttu-id="8b84d-169">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-169">String</span></span>|  
|<span data-ttu-id="8b84d-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-170">DATA_TYPE</span></span>|<span data-ttu-id="8b84d-171">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-171">Int16</span></span>|  
|<span data-ttu-id="8b84d-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-172">TYPE_NAME</span></span>|<span data-ttu-id="8b84d-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-173">String</span></span>|  
|<span data-ttu-id="8b84d-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="8b84d-174">COLUMN_SIZE</span></span>|<span data-ttu-id="8b84d-175">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-175">Int32</span></span>|  
|<span data-ttu-id="8b84d-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="8b84d-177">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-177">Int32</span></span>|  
|<span data-ttu-id="8b84d-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="8b84d-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="8b84d-179">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-179">Int16</span></span>|  
|<span data-ttu-id="8b84d-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="8b84d-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="8b84d-181">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-181">Int16</span></span>|  
|<span data-ttu-id="8b84d-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-182">NULLABLE</span></span>|<span data-ttu-id="8b84d-183">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-183">Int16</span></span>|  
|<span data-ttu-id="8b84d-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-184">REMARKS</span></span>|<span data-ttu-id="8b84d-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-185">String</span></span>|  
|<span data-ttu-id="8b84d-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="8b84d-186">COLUMN_DEF</span></span>|<span data-ttu-id="8b84d-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-187">String</span></span>|  
|<span data-ttu-id="8b84d-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="8b84d-189">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-189">Int16</span></span>|  
|<span data-ttu-id="8b84d-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="8b84d-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="8b84d-191">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-191">Int16</span></span>|  
|<span data-ttu-id="8b84d-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="8b84d-193">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-193">Int32</span></span>|  
|<span data-ttu-id="8b84d-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8b84d-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="8b84d-195">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-195">Int32</span></span>|  
|<span data-ttu-id="8b84d-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-196">IS_NULLABLE</span></span>|<span data-ttu-id="8b84d-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-197">String</span></span>|  
|<span data-ttu-id="8b84d-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8b84d-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="8b84d-199">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-199">String</span></span>|  
|<span data-ttu-id="8b84d-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8b84d-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="8b84d-201">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-201">String</span></span>|  
|<span data-ttu-id="8b84d-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="8b84d-203">Byte</span><span class="sxs-lookup"><span data-stu-id="8b84d-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="8b84d-204">Verfahren</span><span class="sxs-lookup"><span data-stu-id="8b84d-204">Procedures</span></span>  
  
|<span data-ttu-id="8b84d-205">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-205">ColumnName</span></span>|<span data-ttu-id="8b84d-206">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="8b84d-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="8b84d-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-208">String</span></span>|  
|<span data-ttu-id="8b84d-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8b84d-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="8b84d-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-210">String</span></span>|  
|<span data-ttu-id="8b84d-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="8b84d-212">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-212">String</span></span>|  
|<span data-ttu-id="8b84d-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8b84d-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="8b84d-214">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-214">Int32</span></span>|  
|<span data-ttu-id="8b84d-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8b84d-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="8b84d-216">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-216">Int32</span></span>|  
|<span data-ttu-id="8b84d-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="8b84d-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="8b84d-218">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-218">Int32</span></span>|  
|<span data-ttu-id="8b84d-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-219">REMARKS</span></span>|<span data-ttu-id="8b84d-220">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-220">String</span></span>|  
|<span data-ttu-id="8b84d-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8b84d-222">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="8b84d-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8b84d-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="8b84d-224">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-224">ColumnName</span></span>|<span data-ttu-id="8b84d-225">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="8b84d-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="8b84d-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-227">String</span></span>|  
|<span data-ttu-id="8b84d-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8b84d-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="8b84d-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-229">String</span></span>|  
|<span data-ttu-id="8b84d-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="8b84d-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-231">String</span></span>|  
|<span data-ttu-id="8b84d-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-232">COLUMN_NAME</span></span>|<span data-ttu-id="8b84d-233">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-233">String</span></span>|  
|<span data-ttu-id="8b84d-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-234">COLUMN_TYPE</span></span>|<span data-ttu-id="8b84d-235">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-235">Int16</span></span>|  
|<span data-ttu-id="8b84d-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-236">DATA_TYPE</span></span>|<span data-ttu-id="8b84d-237">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-237">Int16</span></span>|  
|<span data-ttu-id="8b84d-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-238">TYPE_NAME</span></span>|<span data-ttu-id="8b84d-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-239">String</span></span>|  
|<span data-ttu-id="8b84d-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="8b84d-240">COLUMN_SIZE</span></span>|<span data-ttu-id="8b84d-241">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-241">Int32</span></span>|  
|<span data-ttu-id="8b84d-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="8b84d-243">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-243">Int32</span></span>|  
|<span data-ttu-id="8b84d-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="8b84d-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="8b84d-245">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-245">Int16</span></span>|  
|<span data-ttu-id="8b84d-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="8b84d-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="8b84d-247">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-247">Int16</span></span>|  
|<span data-ttu-id="8b84d-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-248">NULLABLE</span></span>|<span data-ttu-id="8b84d-249">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-249">Int16</span></span>|  
|<span data-ttu-id="8b84d-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-250">REMARKS</span></span>|<span data-ttu-id="8b84d-251">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-251">String</span></span>|  
|<span data-ttu-id="8b84d-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="8b84d-252">COLUMN_DEF</span></span>|<span data-ttu-id="8b84d-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-253">String</span></span>|  
|<span data-ttu-id="8b84d-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="8b84d-255">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-255">Int16</span></span>|  
|<span data-ttu-id="8b84d-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="8b84d-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="8b84d-257">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-257">Int16</span></span>|  
|<span data-ttu-id="8b84d-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="8b84d-259">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-259">Int32</span></span>|  
|<span data-ttu-id="8b84d-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8b84d-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="8b84d-261">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-261">Int32</span></span>|  
|<span data-ttu-id="8b84d-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-262">IS_NULLABLE</span></span>|<span data-ttu-id="8b84d-263">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-263">String</span></span>|  
|<span data-ttu-id="8b84d-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8b84d-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="8b84d-265">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-265">String</span></span>|  
|<span data-ttu-id="8b84d-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8b84d-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="8b84d-267">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-267">String</span></span>|  
|<span data-ttu-id="8b84d-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="8b84d-269">Byte</span><span class="sxs-lookup"><span data-stu-id="8b84d-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="8b84d-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8b84d-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="8b84d-271">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-271">ColumnName</span></span>|<span data-ttu-id="8b84d-272">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="8b84d-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="8b84d-274">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-274">String</span></span>|  
|<span data-ttu-id="8b84d-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8b84d-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="8b84d-276">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-276">String</span></span>|  
|<span data-ttu-id="8b84d-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="8b84d-278">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-278">String</span></span>|  
|<span data-ttu-id="8b84d-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-279">COLUMN_NAME</span></span>|<span data-ttu-id="8b84d-280">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-280">String</span></span>|  
|<span data-ttu-id="8b84d-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-281">COLUMN_TYPE</span></span>|<span data-ttu-id="8b84d-282">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-282">Int16</span></span>|  
|<span data-ttu-id="8b84d-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-283">DATA_TYPE</span></span>|<span data-ttu-id="8b84d-284">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-284">Int16</span></span>|  
|<span data-ttu-id="8b84d-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-285">TYPE_NAME</span></span>|<span data-ttu-id="8b84d-286">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-286">String</span></span>|  
|<span data-ttu-id="8b84d-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="8b84d-287">COLUMN_SIZE</span></span>|<span data-ttu-id="8b84d-288">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-288">Int32</span></span>|  
|<span data-ttu-id="8b84d-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="8b84d-290">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-290">Int32</span></span>|  
|<span data-ttu-id="8b84d-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="8b84d-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="8b84d-292">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-292">Int16</span></span>|  
|<span data-ttu-id="8b84d-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="8b84d-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="8b84d-294">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-294">Int16</span></span>|  
|<span data-ttu-id="8b84d-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-295">NULLABLE</span></span>|<span data-ttu-id="8b84d-296">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-296">Int16</span></span>|  
|<span data-ttu-id="8b84d-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-297">REMARKS</span></span>|<span data-ttu-id="8b84d-298">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-298">String</span></span>|  
|<span data-ttu-id="8b84d-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="8b84d-299">COLUMN_DEF</span></span>|<span data-ttu-id="8b84d-300">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-300">String</span></span>|  
|<span data-ttu-id="8b84d-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="8b84d-302">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-302">Int16</span></span>|  
|<span data-ttu-id="8b84d-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="8b84d-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="8b84d-304">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-304">Int16</span></span>|  
|<span data-ttu-id="8b84d-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="8b84d-306">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-306">Int32</span></span>|  
|<span data-ttu-id="8b84d-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8b84d-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="8b84d-308">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-308">Int32</span></span>|  
|<span data-ttu-id="8b84d-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-309">IS_NULLABLE</span></span>|<span data-ttu-id="8b84d-310">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-310">String</span></span>|  
|<span data-ttu-id="8b84d-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8b84d-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="8b84d-312">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-312">String</span></span>|  
|<span data-ttu-id="8b84d-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8b84d-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="8b84d-314">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-314">String</span></span>|  
|<span data-ttu-id="8b84d-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="8b84d-316">Byte</span><span class="sxs-lookup"><span data-stu-id="8b84d-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="8b84d-317">Microsoft Oracle ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="8b84d-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="8b84d-318">Microsoft SQL Server Oracle ODBC-Treiber unterstützt die folgenden spezifischen schemaauflistungen zusätzlich zu den allgemeinen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="8b84d-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="8b84d-319">Tabellen</span><span class="sxs-lookup"><span data-stu-id="8b84d-319">Tables</span></span>  
  
-   <span data-ttu-id="8b84d-320">Columns</span><span class="sxs-lookup"><span data-stu-id="8b84d-320">Columns</span></span>  
  
-   <span data-ttu-id="8b84d-321">Verfahren</span><span class="sxs-lookup"><span data-stu-id="8b84d-321">Procedures</span></span>  
  
-   <span data-ttu-id="8b84d-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8b84d-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="8b84d-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8b84d-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="8b84d-324">Ansichten</span><span class="sxs-lookup"><span data-stu-id="8b84d-324">Views</span></span>  
  
-   <span data-ttu-id="8b84d-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="8b84d-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="8b84d-326">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="8b84d-326">Tables and Views</span></span>  
  
|<span data-ttu-id="8b84d-327">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-327">ColumnName</span></span>|<span data-ttu-id="8b84d-328">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8b84d-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="8b84d-330">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-330">String</span></span>|  
|<span data-ttu-id="8b84d-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b84d-331">TABLE_OWNER</span></span>|<span data-ttu-id="8b84d-332">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-332">String</span></span>|  
|<span data-ttu-id="8b84d-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-333">TABLE_NAME</span></span>|<span data-ttu-id="8b84d-334">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-334">String</span></span>|  
|<span data-ttu-id="8b84d-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-335">TABLE_TYPE</span></span>|<span data-ttu-id="8b84d-336">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-336">String</span></span>|  
|<span data-ttu-id="8b84d-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-337">REMARKS</span></span>|<span data-ttu-id="8b84d-338">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="8b84d-339">Columns</span><span class="sxs-lookup"><span data-stu-id="8b84d-339">Columns</span></span>  
  
|<span data-ttu-id="8b84d-340">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-340">ColumnName</span></span>|<span data-ttu-id="8b84d-341">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8b84d-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="8b84d-343">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-343">String</span></span>|  
|<span data-ttu-id="8b84d-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b84d-344">TABLE_OWNER</span></span>|<span data-ttu-id="8b84d-345">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-345">String</span></span>|  
|<span data-ttu-id="8b84d-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-346">TABLE_NAME</span></span>|<span data-ttu-id="8b84d-347">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-347">String</span></span>|  
|<span data-ttu-id="8b84d-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-348">COLUMN_NAME</span></span>|<span data-ttu-id="8b84d-349">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-349">String</span></span>|  
|<span data-ttu-id="8b84d-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-350">DATA_TYPE</span></span>|<span data-ttu-id="8b84d-351">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-351">Int16</span></span>|  
|<span data-ttu-id="8b84d-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-352">TYPE_NAME</span></span>|<span data-ttu-id="8b84d-353">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-353">String</span></span>|  
|<span data-ttu-id="8b84d-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="8b84d-354">PRECISION</span></span>|<span data-ttu-id="8b84d-355">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-355">Int32</span></span>|  
|<span data-ttu-id="8b84d-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-356">LENGTH</span></span>|<span data-ttu-id="8b84d-357">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-357">Int32</span></span>|  
|<span data-ttu-id="8b84d-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="8b84d-358">SCALE</span></span>|<span data-ttu-id="8b84d-359">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-359">Int16</span></span>|  
|<span data-ttu-id="8b84d-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="8b84d-360">RADIX</span></span>|<span data-ttu-id="8b84d-361">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-361">Int16</span></span>|  
|<span data-ttu-id="8b84d-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-362">NULLABLE</span></span>|<span data-ttu-id="8b84d-363">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-363">Int16</span></span>|  
|<span data-ttu-id="8b84d-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-364">REMARKS</span></span>|<span data-ttu-id="8b84d-365">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-365">String</span></span>|  
|<span data-ttu-id="8b84d-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8b84d-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="8b84d-367">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="8b84d-368">Verfahren</span><span class="sxs-lookup"><span data-stu-id="8b84d-368">Procedures</span></span>  
  
|<span data-ttu-id="8b84d-369">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-369">ColumnName</span></span>|<span data-ttu-id="8b84d-370">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8b84d-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="8b84d-372">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-372">String</span></span>|  
|<span data-ttu-id="8b84d-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b84d-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="8b84d-374">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-374">String</span></span>|  
|<span data-ttu-id="8b84d-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="8b84d-376">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-376">String</span></span>|  
|<span data-ttu-id="8b84d-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8b84d-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="8b84d-378">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-378">Int16</span></span>|  
|<span data-ttu-id="8b84d-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8b84d-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="8b84d-380">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-380">Int16</span></span>|  
|<span data-ttu-id="8b84d-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="8b84d-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="8b84d-382">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-382">Int16</span></span>|  
|<span data-ttu-id="8b84d-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-383">REMARKS</span></span>|<span data-ttu-id="8b84d-384">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-384">String</span></span>|  
|<span data-ttu-id="8b84d-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8b84d-386">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="8b84d-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8b84d-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="8b84d-388">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-388">ColumnName</span></span>|<span data-ttu-id="8b84d-389">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8b84d-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="8b84d-391">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-391">String</span></span>|  
|<span data-ttu-id="8b84d-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b84d-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="8b84d-393">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-393">String</span></span>|  
|<span data-ttu-id="8b84d-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="8b84d-395">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-395">String</span></span>|  
|<span data-ttu-id="8b84d-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-396">COLUMN_NAME</span></span>|<span data-ttu-id="8b84d-397">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-397">String</span></span>|  
|<span data-ttu-id="8b84d-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-398">COLUMN_TYPE</span></span>|<span data-ttu-id="8b84d-399">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-399">Int16</span></span>|  
|<span data-ttu-id="8b84d-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-400">DATA_TYPE</span></span>|<span data-ttu-id="8b84d-401">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-401">Int16</span></span>|  
|<span data-ttu-id="8b84d-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-402">TYPE_NAME</span></span>|<span data-ttu-id="8b84d-403">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-403">String</span></span>|  
|<span data-ttu-id="8b84d-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="8b84d-404">PRECISION</span></span>|<span data-ttu-id="8b84d-405">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-405">Int32</span></span>|  
|<span data-ttu-id="8b84d-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-406">LENGTH</span></span>|<span data-ttu-id="8b84d-407">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-407">Int32</span></span>|  
|<span data-ttu-id="8b84d-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="8b84d-408">SCALE</span></span>|<span data-ttu-id="8b84d-409">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-409">Int16</span></span>|  
|<span data-ttu-id="8b84d-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="8b84d-410">RADIX</span></span>|<span data-ttu-id="8b84d-411">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-411">Int16</span></span>|  
|<span data-ttu-id="8b84d-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-412">NULLABLE</span></span>|<span data-ttu-id="8b84d-413">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-413">Int16</span></span>|  
|<span data-ttu-id="8b84d-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-414">REMARKS</span></span>|<span data-ttu-id="8b84d-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-415">String</span></span>|  
|<span data-ttu-id="8b84d-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="8b84d-416">OVERLOAD</span></span>|<span data-ttu-id="8b84d-417">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-417">Int32</span></span>|  
|<span data-ttu-id="8b84d-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8b84d-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="8b84d-419">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="8b84d-420">Microsoft Jet ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="8b84d-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="8b84d-421">Der Microsoft Jet ODBC-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="8b84d-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="8b84d-422">Tabellen</span><span class="sxs-lookup"><span data-stu-id="8b84d-422">Tables</span></span>  
  
-   <span data-ttu-id="8b84d-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="8b84d-423">Indexes</span></span>  
  
-   <span data-ttu-id="8b84d-424">Columns</span><span class="sxs-lookup"><span data-stu-id="8b84d-424">Columns</span></span>  
  
-   <span data-ttu-id="8b84d-425">Verfahren</span><span class="sxs-lookup"><span data-stu-id="8b84d-425">Procedures</span></span>  
  
-   <span data-ttu-id="8b84d-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8b84d-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="8b84d-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8b84d-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="8b84d-428">Ansichten</span><span class="sxs-lookup"><span data-stu-id="8b84d-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="8b84d-429">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="8b84d-429">Tables and Views</span></span>  
  
|<span data-ttu-id="8b84d-430">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-430">ColumnName</span></span>|<span data-ttu-id="8b84d-431">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8b84d-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="8b84d-433">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-433">String</span></span>|  
|<span data-ttu-id="8b84d-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b84d-434">TABLE_OWNER</span></span>|<span data-ttu-id="8b84d-435">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-435">String</span></span>|  
|<span data-ttu-id="8b84d-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-436">TABLE_NAME</span></span>|<span data-ttu-id="8b84d-437">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-437">String</span></span>|  
|<span data-ttu-id="8b84d-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-438">TABLE_TYPE</span></span>|<span data-ttu-id="8b84d-439">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-439">String</span></span>|  
|<span data-ttu-id="8b84d-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-440">REMARKS</span></span>|<span data-ttu-id="8b84d-441">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="8b84d-442">Columns</span><span class="sxs-lookup"><span data-stu-id="8b84d-442">Columns</span></span>  
  
|<span data-ttu-id="8b84d-443">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-443">ColumnName</span></span>|<span data-ttu-id="8b84d-444">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8b84d-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="8b84d-446">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-446">String</span></span>|  
|<span data-ttu-id="8b84d-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b84d-447">TABLE_OWNER</span></span>|<span data-ttu-id="8b84d-448">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-448">String</span></span>|  
|<span data-ttu-id="8b84d-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-449">TABLE_NAME</span></span>|<span data-ttu-id="8b84d-450">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-450">String</span></span>|  
|<span data-ttu-id="8b84d-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-451">COLUMN_NAME</span></span>|<span data-ttu-id="8b84d-452">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-452">String</span></span>|  
|<span data-ttu-id="8b84d-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-453">DATA_TYPE</span></span>|<span data-ttu-id="8b84d-454">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-454">Int16</span></span>|  
|<span data-ttu-id="8b84d-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-455">TYPE_NAME</span></span>|<span data-ttu-id="8b84d-456">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-456">String</span></span>|  
|<span data-ttu-id="8b84d-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="8b84d-457">PRECISION</span></span>|<span data-ttu-id="8b84d-458">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-458">Int32</span></span>|  
|<span data-ttu-id="8b84d-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-459">LENGTH</span></span>|<span data-ttu-id="8b84d-460">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-460">Int32</span></span>|  
|<span data-ttu-id="8b84d-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="8b84d-461">SCALE</span></span>|<span data-ttu-id="8b84d-462">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-462">Int16</span></span>|  
|<span data-ttu-id="8b84d-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="8b84d-463">RADIX</span></span>|<span data-ttu-id="8b84d-464">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-464">Int16</span></span>|  
|<span data-ttu-id="8b84d-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-465">NULLABLE</span></span>|<span data-ttu-id="8b84d-466">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-466">Int16</span></span>|  
|<span data-ttu-id="8b84d-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-467">REMARKS</span></span>|<span data-ttu-id="8b84d-468">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-468">String</span></span>|  
|<span data-ttu-id="8b84d-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8b84d-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="8b84d-470">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="8b84d-471">Verfahren</span><span class="sxs-lookup"><span data-stu-id="8b84d-471">Procedures</span></span>  
  
|<span data-ttu-id="8b84d-472">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-472">ColumnName</span></span>|<span data-ttu-id="8b84d-473">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8b84d-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="8b84d-475">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-475">String</span></span>|  
|<span data-ttu-id="8b84d-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b84d-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="8b84d-477">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-477">String</span></span>|  
|<span data-ttu-id="8b84d-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="8b84d-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-479">String</span></span>|  
|<span data-ttu-id="8b84d-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8b84d-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="8b84d-481">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-481">Int16</span></span>|  
|<span data-ttu-id="8b84d-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="8b84d-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="8b84d-483">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-483">Int16</span></span>|  
|<span data-ttu-id="8b84d-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="8b84d-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="8b84d-485">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-485">Int16</span></span>|  
|<span data-ttu-id="8b84d-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-486">REMARKS</span></span>|<span data-ttu-id="8b84d-487">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-487">String</span></span>|  
|<span data-ttu-id="8b84d-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8b84d-489">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="8b84d-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8b84d-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="8b84d-491">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-491">ColumnName</span></span>|<span data-ttu-id="8b84d-492">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="8b84d-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="8b84d-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-494">String</span></span>|  
|<span data-ttu-id="8b84d-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b84d-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="8b84d-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-496">String</span></span>|  
|<span data-ttu-id="8b84d-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="8b84d-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-498">String</span></span>|  
|<span data-ttu-id="8b84d-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-499">COLUMN_NAME</span></span>|<span data-ttu-id="8b84d-500">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-500">String</span></span>|  
|<span data-ttu-id="8b84d-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-501">COLUMN_TYPE</span></span>|<span data-ttu-id="8b84d-502">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-502">Int16</span></span>|  
|<span data-ttu-id="8b84d-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-503">DATA_TYPE</span></span>|<span data-ttu-id="8b84d-504">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-504">Int16</span></span>|  
|<span data-ttu-id="8b84d-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-505">TYPE_NAME</span></span>|<span data-ttu-id="8b84d-506">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-506">String</span></span>|  
|<span data-ttu-id="8b84d-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="8b84d-507">PRECISION</span></span>|<span data-ttu-id="8b84d-508">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-508">Int32</span></span>|  
|<span data-ttu-id="8b84d-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-509">LENGTH</span></span>|<span data-ttu-id="8b84d-510">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-510">Int32</span></span>|  
|<span data-ttu-id="8b84d-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="8b84d-511">SCALE</span></span>|<span data-ttu-id="8b84d-512">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-512">Int16</span></span>|  
|<span data-ttu-id="8b84d-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="8b84d-513">RADIX</span></span>|<span data-ttu-id="8b84d-514">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-514">Int16</span></span>|  
|<span data-ttu-id="8b84d-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-515">NULLABLE</span></span>|<span data-ttu-id="8b84d-516">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-516">Int16</span></span>|  
|<span data-ttu-id="8b84d-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-517">REMARKS</span></span>|<span data-ttu-id="8b84d-518">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-518">String</span></span>|  
|<span data-ttu-id="8b84d-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="8b84d-519">OVERLOAD</span></span>|<span data-ttu-id="8b84d-520">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-520">Int32</span></span>|  
|<span data-ttu-id="8b84d-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8b84d-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="8b84d-522">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="8b84d-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8b84d-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="8b84d-524">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="8b84d-524">ColumnName</span></span>|<span data-ttu-id="8b84d-525">DataType</span><span class="sxs-lookup"><span data-stu-id="8b84d-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8b84d-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="8b84d-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="8b84d-527">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-527">String</span></span>|  
|<span data-ttu-id="8b84d-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="8b84d-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="8b84d-529">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-529">String</span></span>|  
|<span data-ttu-id="8b84d-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="8b84d-531">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-531">String</span></span>|  
|<span data-ttu-id="8b84d-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-532">COLUMN_NAME</span></span>|<span data-ttu-id="8b84d-533">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-533">String</span></span>|  
|<span data-ttu-id="8b84d-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-534">COLUMN_TYPE</span></span>|<span data-ttu-id="8b84d-535">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-535">Int16</span></span>|  
|<span data-ttu-id="8b84d-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-536">DATA_TYPE</span></span>|<span data-ttu-id="8b84d-537">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-537">Int16</span></span>|  
|<span data-ttu-id="8b84d-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8b84d-538">TYPE_NAME</span></span>|<span data-ttu-id="8b84d-539">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-539">String</span></span>|  
|<span data-ttu-id="8b84d-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="8b84d-540">COLUMN_SIZE</span></span>|<span data-ttu-id="8b84d-541">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-541">Int32</span></span>|  
|<span data-ttu-id="8b84d-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="8b84d-543">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-543">Int32</span></span>|  
|<span data-ttu-id="8b84d-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="8b84d-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="8b84d-545">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-545">Int16</span></span>|  
|<span data-ttu-id="8b84d-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="8b84d-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="8b84d-547">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-547">Int16</span></span>|  
|<span data-ttu-id="8b84d-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-548">NULLABLE</span></span>|<span data-ttu-id="8b84d-549">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-549">Int16</span></span>|  
|<span data-ttu-id="8b84d-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="8b84d-550">REMARKS</span></span>|<span data-ttu-id="8b84d-551">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-551">String</span></span>|  
|<span data-ttu-id="8b84d-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="8b84d-552">COLUMN_DEF</span></span>|<span data-ttu-id="8b84d-553">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-553">String</span></span>|  
|<span data-ttu-id="8b84d-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8b84d-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="8b84d-555">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-555">Int16</span></span>|  
|<span data-ttu-id="8b84d-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="8b84d-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="8b84d-557">Int16</span><span class="sxs-lookup"><span data-stu-id="8b84d-557">Int16</span></span>|  
|<span data-ttu-id="8b84d-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8b84d-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="8b84d-559">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-559">Int32</span></span>|  
|<span data-ttu-id="8b84d-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8b84d-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="8b84d-561">Int32</span><span class="sxs-lookup"><span data-stu-id="8b84d-561">Int32</span></span>|  
|<span data-ttu-id="8b84d-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8b84d-562">IS_NULLABLE</span></span>|<span data-ttu-id="8b84d-563">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b84d-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b84d-564">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b84d-564">See Also</span></span>  
 [<span data-ttu-id="8b84d-565">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="8b84d-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
