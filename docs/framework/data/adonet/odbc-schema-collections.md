---
title: ODBC-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43479979"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="822fe-102">ODBC-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="822fe-102">ODBC Schema Collections</span></span>
<span data-ttu-id="822fe-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Treiber für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="822fe-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="822fe-104">Microsoft SQL Server-ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="822fe-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="822fe-105">Der Microsoft SQL Server-ODBC-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="822fe-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="822fe-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="822fe-106">Tables</span></span>  
  
-   <span data-ttu-id="822fe-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="822fe-107">Indexes</span></span>  
  
-   <span data-ttu-id="822fe-108">Columns</span><span class="sxs-lookup"><span data-stu-id="822fe-108">Columns</span></span>  
  
-   <span data-ttu-id="822fe-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="822fe-109">Procedures</span></span>  
  
-   <span data-ttu-id="822fe-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="822fe-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="822fe-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="822fe-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="822fe-112">Ansichten</span><span class="sxs-lookup"><span data-stu-id="822fe-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="822fe-113">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="822fe-113">Tables and Views</span></span>  
  
|<span data-ttu-id="822fe-114">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-114">ColumnName</span></span>|<span data-ttu-id="822fe-115">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="822fe-116">TABLE_CAT</span></span>|<span data-ttu-id="822fe-117">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-117">String</span></span>|  
|<span data-ttu-id="822fe-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="822fe-118">TABLE_SCHEM</span></span>|<span data-ttu-id="822fe-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-119">String</span></span>|  
|<span data-ttu-id="822fe-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-120">TABLE_NAME</span></span>|<span data-ttu-id="822fe-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-121">String</span></span>|  
|<span data-ttu-id="822fe-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-122">TABLE_TYPE</span></span>|<span data-ttu-id="822fe-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-123">String</span></span>|  
|<span data-ttu-id="822fe-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-124">REMARKS</span></span>|<span data-ttu-id="822fe-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="822fe-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="822fe-126">Indexes</span></span>  
  
|<span data-ttu-id="822fe-127">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-127">ColumnName</span></span>|<span data-ttu-id="822fe-128">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="822fe-129">TABLE_CAT</span></span>|<span data-ttu-id="822fe-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-130">String</span></span>|  
|<span data-ttu-id="822fe-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="822fe-131">TABLE_SCHEM</span></span>|<span data-ttu-id="822fe-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-132">String</span></span>|  
|<span data-ttu-id="822fe-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-133">TABLE_NAME</span></span>|<span data-ttu-id="822fe-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-134">String</span></span>|  
|<span data-ttu-id="822fe-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="822fe-135">NON_UNIQUE</span></span>|<span data-ttu-id="822fe-136">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-136">Int16</span></span>|  
|<span data-ttu-id="822fe-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="822fe-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="822fe-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-138">String</span></span>|  
|<span data-ttu-id="822fe-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-139">INDEX_NAME</span></span>|<span data-ttu-id="822fe-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-140">String</span></span>|  
|<span data-ttu-id="822fe-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-141">TYPE</span></span>|<span data-ttu-id="822fe-142">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-142">Int16</span></span>|  
|<span data-ttu-id="822fe-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="822fe-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="822fe-144">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-144">Int16</span></span>|  
|<span data-ttu-id="822fe-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-145">COLUMN_NAME</span></span>|<span data-ttu-id="822fe-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-146">String</span></span>|  
|<span data-ttu-id="822fe-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="822fe-147">ASC_OR_DESC</span></span>|<span data-ttu-id="822fe-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-148">String</span></span>|  
|<span data-ttu-id="822fe-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="822fe-149">CARDINATLITY</span></span>|<span data-ttu-id="822fe-150">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-150">Int32</span></span>|  
|<span data-ttu-id="822fe-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="822fe-151">PAGES</span></span>|<span data-ttu-id="822fe-152">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-152">Int32</span></span>|  
|<span data-ttu-id="822fe-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="822fe-153">FILTER_CONDITION</span></span>|<span data-ttu-id="822fe-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-154">String</span></span>|  
|<span data-ttu-id="822fe-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="822fe-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="822fe-156">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-156">String</span></span>|  
|<span data-ttu-id="822fe-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="822fe-158">Byte</span><span class="sxs-lookup"><span data-stu-id="822fe-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="822fe-159">Columns</span><span class="sxs-lookup"><span data-stu-id="822fe-159">Columns</span></span>  
  
|<span data-ttu-id="822fe-160">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-160">ColumnName</span></span>|<span data-ttu-id="822fe-161">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="822fe-162">TABLE_CAT</span></span>|<span data-ttu-id="822fe-163">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-163">String</span></span>|  
|<span data-ttu-id="822fe-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="822fe-164">TABLE_SCHEM</span></span>|<span data-ttu-id="822fe-165">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-165">String</span></span>|  
|<span data-ttu-id="822fe-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-166">TABLE_NAME</span></span>|<span data-ttu-id="822fe-167">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-167">String</span></span>|  
|<span data-ttu-id="822fe-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-168">COLUMN_NAME</span></span>|<span data-ttu-id="822fe-169">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-169">String</span></span>|  
|<span data-ttu-id="822fe-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-170">DATA_TYPE</span></span>|<span data-ttu-id="822fe-171">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-171">Int16</span></span>|  
|<span data-ttu-id="822fe-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-172">TYPE_NAME</span></span>|<span data-ttu-id="822fe-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-173">String</span></span>|  
|<span data-ttu-id="822fe-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="822fe-174">COLUMN_SIZE</span></span>|<span data-ttu-id="822fe-175">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-175">Int32</span></span>|  
|<span data-ttu-id="822fe-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="822fe-177">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-177">Int32</span></span>|  
|<span data-ttu-id="822fe-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="822fe-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="822fe-179">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-179">Int16</span></span>|  
|<span data-ttu-id="822fe-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="822fe-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="822fe-181">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-181">Int16</span></span>|  
|<span data-ttu-id="822fe-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-182">NULLABLE</span></span>|<span data-ttu-id="822fe-183">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-183">Int16</span></span>|  
|<span data-ttu-id="822fe-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-184">REMARKS</span></span>|<span data-ttu-id="822fe-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-185">String</span></span>|  
|<span data-ttu-id="822fe-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="822fe-186">COLUMN_DEF</span></span>|<span data-ttu-id="822fe-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-187">String</span></span>|  
|<span data-ttu-id="822fe-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="822fe-189">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-189">Int16</span></span>|  
|<span data-ttu-id="822fe-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="822fe-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="822fe-191">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-191">Int16</span></span>|  
|<span data-ttu-id="822fe-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="822fe-193">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-193">Int32</span></span>|  
|<span data-ttu-id="822fe-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="822fe-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="822fe-195">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-195">Int32</span></span>|  
|<span data-ttu-id="822fe-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-196">IS_NULLABLE</span></span>|<span data-ttu-id="822fe-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-197">String</span></span>|  
|<span data-ttu-id="822fe-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="822fe-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="822fe-199">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-199">String</span></span>|  
|<span data-ttu-id="822fe-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="822fe-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="822fe-201">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-201">String</span></span>|  
|<span data-ttu-id="822fe-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="822fe-203">Byte</span><span class="sxs-lookup"><span data-stu-id="822fe-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="822fe-204">Verfahren</span><span class="sxs-lookup"><span data-stu-id="822fe-204">Procedures</span></span>  
  
|<span data-ttu-id="822fe-205">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-205">ColumnName</span></span>|<span data-ttu-id="822fe-206">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="822fe-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="822fe-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-208">String</span></span>|  
|<span data-ttu-id="822fe-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="822fe-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="822fe-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-210">String</span></span>|  
|<span data-ttu-id="822fe-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="822fe-212">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-212">String</span></span>|  
|<span data-ttu-id="822fe-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="822fe-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="822fe-214">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-214">Int32</span></span>|  
|<span data-ttu-id="822fe-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="822fe-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="822fe-216">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-216">Int32</span></span>|  
|<span data-ttu-id="822fe-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="822fe-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="822fe-218">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-218">Int32</span></span>|  
|<span data-ttu-id="822fe-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-219">REMARKS</span></span>|<span data-ttu-id="822fe-220">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-220">String</span></span>|  
|<span data-ttu-id="822fe-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="822fe-222">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="822fe-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="822fe-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="822fe-224">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-224">ColumnName</span></span>|<span data-ttu-id="822fe-225">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="822fe-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="822fe-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-227">String</span></span>|  
|<span data-ttu-id="822fe-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="822fe-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="822fe-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-229">String</span></span>|  
|<span data-ttu-id="822fe-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="822fe-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-231">String</span></span>|  
|<span data-ttu-id="822fe-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-232">COLUMN_NAME</span></span>|<span data-ttu-id="822fe-233">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-233">String</span></span>|  
|<span data-ttu-id="822fe-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-234">COLUMN_TYPE</span></span>|<span data-ttu-id="822fe-235">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-235">Int16</span></span>|  
|<span data-ttu-id="822fe-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-236">DATA_TYPE</span></span>|<span data-ttu-id="822fe-237">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-237">Int16</span></span>|  
|<span data-ttu-id="822fe-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-238">TYPE_NAME</span></span>|<span data-ttu-id="822fe-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-239">String</span></span>|  
|<span data-ttu-id="822fe-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="822fe-240">COLUMN_SIZE</span></span>|<span data-ttu-id="822fe-241">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-241">Int32</span></span>|  
|<span data-ttu-id="822fe-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="822fe-243">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-243">Int32</span></span>|  
|<span data-ttu-id="822fe-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="822fe-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="822fe-245">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-245">Int16</span></span>|  
|<span data-ttu-id="822fe-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="822fe-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="822fe-247">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-247">Int16</span></span>|  
|<span data-ttu-id="822fe-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-248">NULLABLE</span></span>|<span data-ttu-id="822fe-249">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-249">Int16</span></span>|  
|<span data-ttu-id="822fe-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-250">REMARKS</span></span>|<span data-ttu-id="822fe-251">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-251">String</span></span>|  
|<span data-ttu-id="822fe-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="822fe-252">COLUMN_DEF</span></span>|<span data-ttu-id="822fe-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-253">String</span></span>|  
|<span data-ttu-id="822fe-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="822fe-255">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-255">Int16</span></span>|  
|<span data-ttu-id="822fe-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="822fe-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="822fe-257">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-257">Int16</span></span>|  
|<span data-ttu-id="822fe-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="822fe-259">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-259">Int32</span></span>|  
|<span data-ttu-id="822fe-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="822fe-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="822fe-261">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-261">Int32</span></span>|  
|<span data-ttu-id="822fe-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-262">IS_NULLABLE</span></span>|<span data-ttu-id="822fe-263">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-263">String</span></span>|  
|<span data-ttu-id="822fe-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="822fe-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="822fe-265">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-265">String</span></span>|  
|<span data-ttu-id="822fe-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="822fe-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="822fe-267">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-267">String</span></span>|  
|<span data-ttu-id="822fe-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="822fe-269">Byte</span><span class="sxs-lookup"><span data-stu-id="822fe-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="822fe-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="822fe-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="822fe-271">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-271">ColumnName</span></span>|<span data-ttu-id="822fe-272">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="822fe-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="822fe-274">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-274">String</span></span>|  
|<span data-ttu-id="822fe-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="822fe-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="822fe-276">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-276">String</span></span>|  
|<span data-ttu-id="822fe-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="822fe-278">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-278">String</span></span>|  
|<span data-ttu-id="822fe-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-279">COLUMN_NAME</span></span>|<span data-ttu-id="822fe-280">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-280">String</span></span>|  
|<span data-ttu-id="822fe-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-281">COLUMN_TYPE</span></span>|<span data-ttu-id="822fe-282">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-282">Int16</span></span>|  
|<span data-ttu-id="822fe-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-283">DATA_TYPE</span></span>|<span data-ttu-id="822fe-284">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-284">Int16</span></span>|  
|<span data-ttu-id="822fe-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-285">TYPE_NAME</span></span>|<span data-ttu-id="822fe-286">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-286">String</span></span>|  
|<span data-ttu-id="822fe-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="822fe-287">COLUMN_SIZE</span></span>|<span data-ttu-id="822fe-288">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-288">Int32</span></span>|  
|<span data-ttu-id="822fe-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="822fe-290">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-290">Int32</span></span>|  
|<span data-ttu-id="822fe-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="822fe-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="822fe-292">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-292">Int16</span></span>|  
|<span data-ttu-id="822fe-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="822fe-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="822fe-294">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-294">Int16</span></span>|  
|<span data-ttu-id="822fe-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-295">NULLABLE</span></span>|<span data-ttu-id="822fe-296">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-296">Int16</span></span>|  
|<span data-ttu-id="822fe-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-297">REMARKS</span></span>|<span data-ttu-id="822fe-298">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-298">String</span></span>|  
|<span data-ttu-id="822fe-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="822fe-299">COLUMN_DEF</span></span>|<span data-ttu-id="822fe-300">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-300">String</span></span>|  
|<span data-ttu-id="822fe-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="822fe-302">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-302">Int16</span></span>|  
|<span data-ttu-id="822fe-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="822fe-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="822fe-304">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-304">Int16</span></span>|  
|<span data-ttu-id="822fe-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="822fe-306">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-306">Int32</span></span>|  
|<span data-ttu-id="822fe-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="822fe-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="822fe-308">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-308">Int32</span></span>|  
|<span data-ttu-id="822fe-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-309">IS_NULLABLE</span></span>|<span data-ttu-id="822fe-310">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-310">String</span></span>|  
|<span data-ttu-id="822fe-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="822fe-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="822fe-312">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-312">String</span></span>|  
|<span data-ttu-id="822fe-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="822fe-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="822fe-314">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-314">String</span></span>|  
|<span data-ttu-id="822fe-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="822fe-316">Byte</span><span class="sxs-lookup"><span data-stu-id="822fe-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="822fe-317">Microsoft Oracle ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="822fe-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="822fe-318">Der Microsoft SQL Server Oracle ODBC-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="822fe-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="822fe-319">Tabellen</span><span class="sxs-lookup"><span data-stu-id="822fe-319">Tables</span></span>  
  
-   <span data-ttu-id="822fe-320">Columns</span><span class="sxs-lookup"><span data-stu-id="822fe-320">Columns</span></span>  
  
-   <span data-ttu-id="822fe-321">Verfahren</span><span class="sxs-lookup"><span data-stu-id="822fe-321">Procedures</span></span>  
  
-   <span data-ttu-id="822fe-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="822fe-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="822fe-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="822fe-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="822fe-324">Ansichten</span><span class="sxs-lookup"><span data-stu-id="822fe-324">Views</span></span>  
  
-   <span data-ttu-id="822fe-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="822fe-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="822fe-326">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="822fe-326">Tables and Views</span></span>  
  
|<span data-ttu-id="822fe-327">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-327">ColumnName</span></span>|<span data-ttu-id="822fe-328">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="822fe-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="822fe-330">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-330">String</span></span>|  
|<span data-ttu-id="822fe-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="822fe-331">TABLE_OWNER</span></span>|<span data-ttu-id="822fe-332">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-332">String</span></span>|  
|<span data-ttu-id="822fe-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-333">TABLE_NAME</span></span>|<span data-ttu-id="822fe-334">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-334">String</span></span>|  
|<span data-ttu-id="822fe-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-335">TABLE_TYPE</span></span>|<span data-ttu-id="822fe-336">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-336">String</span></span>|  
|<span data-ttu-id="822fe-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-337">REMARKS</span></span>|<span data-ttu-id="822fe-338">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="822fe-339">Columns</span><span class="sxs-lookup"><span data-stu-id="822fe-339">Columns</span></span>  
  
|<span data-ttu-id="822fe-340">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-340">ColumnName</span></span>|<span data-ttu-id="822fe-341">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="822fe-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="822fe-343">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-343">String</span></span>|  
|<span data-ttu-id="822fe-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="822fe-344">TABLE_OWNER</span></span>|<span data-ttu-id="822fe-345">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-345">String</span></span>|  
|<span data-ttu-id="822fe-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-346">TABLE_NAME</span></span>|<span data-ttu-id="822fe-347">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-347">String</span></span>|  
|<span data-ttu-id="822fe-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-348">COLUMN_NAME</span></span>|<span data-ttu-id="822fe-349">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-349">String</span></span>|  
|<span data-ttu-id="822fe-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-350">DATA_TYPE</span></span>|<span data-ttu-id="822fe-351">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-351">Int16</span></span>|  
|<span data-ttu-id="822fe-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-352">TYPE_NAME</span></span>|<span data-ttu-id="822fe-353">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-353">String</span></span>|  
|<span data-ttu-id="822fe-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="822fe-354">PRECISION</span></span>|<span data-ttu-id="822fe-355">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-355">Int32</span></span>|  
|<span data-ttu-id="822fe-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-356">LENGTH</span></span>|<span data-ttu-id="822fe-357">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-357">Int32</span></span>|  
|<span data-ttu-id="822fe-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="822fe-358">SCALE</span></span>|<span data-ttu-id="822fe-359">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-359">Int16</span></span>|  
|<span data-ttu-id="822fe-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="822fe-360">RADIX</span></span>|<span data-ttu-id="822fe-361">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-361">Int16</span></span>|  
|<span data-ttu-id="822fe-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-362">NULLABLE</span></span>|<span data-ttu-id="822fe-363">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-363">Int16</span></span>|  
|<span data-ttu-id="822fe-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-364">REMARKS</span></span>|<span data-ttu-id="822fe-365">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-365">String</span></span>|  
|<span data-ttu-id="822fe-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="822fe-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="822fe-367">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="822fe-368">Verfahren</span><span class="sxs-lookup"><span data-stu-id="822fe-368">Procedures</span></span>  
  
|<span data-ttu-id="822fe-369">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-369">ColumnName</span></span>|<span data-ttu-id="822fe-370">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="822fe-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="822fe-372">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-372">String</span></span>|  
|<span data-ttu-id="822fe-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="822fe-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="822fe-374">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-374">String</span></span>|  
|<span data-ttu-id="822fe-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="822fe-376">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-376">String</span></span>|  
|<span data-ttu-id="822fe-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="822fe-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="822fe-378">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-378">Int16</span></span>|  
|<span data-ttu-id="822fe-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="822fe-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="822fe-380">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-380">Int16</span></span>|  
|<span data-ttu-id="822fe-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="822fe-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="822fe-382">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-382">Int16</span></span>|  
|<span data-ttu-id="822fe-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-383">REMARKS</span></span>|<span data-ttu-id="822fe-384">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-384">String</span></span>|  
|<span data-ttu-id="822fe-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="822fe-386">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="822fe-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="822fe-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="822fe-388">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-388">ColumnName</span></span>|<span data-ttu-id="822fe-389">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="822fe-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="822fe-391">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-391">String</span></span>|  
|<span data-ttu-id="822fe-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="822fe-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="822fe-393">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-393">String</span></span>|  
|<span data-ttu-id="822fe-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="822fe-395">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-395">String</span></span>|  
|<span data-ttu-id="822fe-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-396">COLUMN_NAME</span></span>|<span data-ttu-id="822fe-397">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-397">String</span></span>|  
|<span data-ttu-id="822fe-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-398">COLUMN_TYPE</span></span>|<span data-ttu-id="822fe-399">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-399">Int16</span></span>|  
|<span data-ttu-id="822fe-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-400">DATA_TYPE</span></span>|<span data-ttu-id="822fe-401">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-401">Int16</span></span>|  
|<span data-ttu-id="822fe-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-402">TYPE_NAME</span></span>|<span data-ttu-id="822fe-403">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-403">String</span></span>|  
|<span data-ttu-id="822fe-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="822fe-404">PRECISION</span></span>|<span data-ttu-id="822fe-405">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-405">Int32</span></span>|  
|<span data-ttu-id="822fe-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-406">LENGTH</span></span>|<span data-ttu-id="822fe-407">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-407">Int32</span></span>|  
|<span data-ttu-id="822fe-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="822fe-408">SCALE</span></span>|<span data-ttu-id="822fe-409">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-409">Int16</span></span>|  
|<span data-ttu-id="822fe-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="822fe-410">RADIX</span></span>|<span data-ttu-id="822fe-411">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-411">Int16</span></span>|  
|<span data-ttu-id="822fe-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-412">NULLABLE</span></span>|<span data-ttu-id="822fe-413">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-413">Int16</span></span>|  
|<span data-ttu-id="822fe-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-414">REMARKS</span></span>|<span data-ttu-id="822fe-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-415">String</span></span>|  
|<span data-ttu-id="822fe-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="822fe-416">OVERLOAD</span></span>|<span data-ttu-id="822fe-417">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-417">Int32</span></span>|  
|<span data-ttu-id="822fe-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="822fe-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="822fe-419">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="822fe-420">Microsoft Jet ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="822fe-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="822fe-421">Der Microsoft Jet ODBC-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="822fe-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="822fe-422">Tabellen</span><span class="sxs-lookup"><span data-stu-id="822fe-422">Tables</span></span>  
  
-   <span data-ttu-id="822fe-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="822fe-423">Indexes</span></span>  
  
-   <span data-ttu-id="822fe-424">Columns</span><span class="sxs-lookup"><span data-stu-id="822fe-424">Columns</span></span>  
  
-   <span data-ttu-id="822fe-425">Verfahren</span><span class="sxs-lookup"><span data-stu-id="822fe-425">Procedures</span></span>  
  
-   <span data-ttu-id="822fe-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="822fe-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="822fe-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="822fe-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="822fe-428">Ansichten</span><span class="sxs-lookup"><span data-stu-id="822fe-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="822fe-429">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="822fe-429">Tables and Views</span></span>  
  
|<span data-ttu-id="822fe-430">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-430">ColumnName</span></span>|<span data-ttu-id="822fe-431">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="822fe-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="822fe-433">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-433">String</span></span>|  
|<span data-ttu-id="822fe-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="822fe-434">TABLE_OWNER</span></span>|<span data-ttu-id="822fe-435">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-435">String</span></span>|  
|<span data-ttu-id="822fe-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-436">TABLE_NAME</span></span>|<span data-ttu-id="822fe-437">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-437">String</span></span>|  
|<span data-ttu-id="822fe-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-438">TABLE_TYPE</span></span>|<span data-ttu-id="822fe-439">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-439">String</span></span>|  
|<span data-ttu-id="822fe-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-440">REMARKS</span></span>|<span data-ttu-id="822fe-441">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="822fe-442">Columns</span><span class="sxs-lookup"><span data-stu-id="822fe-442">Columns</span></span>  
  
|<span data-ttu-id="822fe-443">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-443">ColumnName</span></span>|<span data-ttu-id="822fe-444">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="822fe-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="822fe-446">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-446">String</span></span>|  
|<span data-ttu-id="822fe-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="822fe-447">TABLE_OWNER</span></span>|<span data-ttu-id="822fe-448">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-448">String</span></span>|  
|<span data-ttu-id="822fe-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-449">TABLE_NAME</span></span>|<span data-ttu-id="822fe-450">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-450">String</span></span>|  
|<span data-ttu-id="822fe-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-451">COLUMN_NAME</span></span>|<span data-ttu-id="822fe-452">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-452">String</span></span>|  
|<span data-ttu-id="822fe-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-453">DATA_TYPE</span></span>|<span data-ttu-id="822fe-454">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-454">Int16</span></span>|  
|<span data-ttu-id="822fe-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-455">TYPE_NAME</span></span>|<span data-ttu-id="822fe-456">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-456">String</span></span>|  
|<span data-ttu-id="822fe-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="822fe-457">PRECISION</span></span>|<span data-ttu-id="822fe-458">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-458">Int32</span></span>|  
|<span data-ttu-id="822fe-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-459">LENGTH</span></span>|<span data-ttu-id="822fe-460">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-460">Int32</span></span>|  
|<span data-ttu-id="822fe-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="822fe-461">SCALE</span></span>|<span data-ttu-id="822fe-462">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-462">Int16</span></span>|  
|<span data-ttu-id="822fe-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="822fe-463">RADIX</span></span>|<span data-ttu-id="822fe-464">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-464">Int16</span></span>|  
|<span data-ttu-id="822fe-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-465">NULLABLE</span></span>|<span data-ttu-id="822fe-466">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-466">Int16</span></span>|  
|<span data-ttu-id="822fe-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-467">REMARKS</span></span>|<span data-ttu-id="822fe-468">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-468">String</span></span>|  
|<span data-ttu-id="822fe-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="822fe-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="822fe-470">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="822fe-471">Verfahren</span><span class="sxs-lookup"><span data-stu-id="822fe-471">Procedures</span></span>  
  
|<span data-ttu-id="822fe-472">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-472">ColumnName</span></span>|<span data-ttu-id="822fe-473">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="822fe-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="822fe-475">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-475">String</span></span>|  
|<span data-ttu-id="822fe-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="822fe-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="822fe-477">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-477">String</span></span>|  
|<span data-ttu-id="822fe-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="822fe-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-479">String</span></span>|  
|<span data-ttu-id="822fe-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="822fe-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="822fe-481">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-481">Int16</span></span>|  
|<span data-ttu-id="822fe-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="822fe-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="822fe-483">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-483">Int16</span></span>|  
|<span data-ttu-id="822fe-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="822fe-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="822fe-485">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-485">Int16</span></span>|  
|<span data-ttu-id="822fe-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-486">REMARKS</span></span>|<span data-ttu-id="822fe-487">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-487">String</span></span>|  
|<span data-ttu-id="822fe-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="822fe-489">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="822fe-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="822fe-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="822fe-491">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-491">ColumnName</span></span>|<span data-ttu-id="822fe-492">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="822fe-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="822fe-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-494">String</span></span>|  
|<span data-ttu-id="822fe-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="822fe-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="822fe-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-496">String</span></span>|  
|<span data-ttu-id="822fe-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="822fe-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-498">String</span></span>|  
|<span data-ttu-id="822fe-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-499">COLUMN_NAME</span></span>|<span data-ttu-id="822fe-500">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-500">String</span></span>|  
|<span data-ttu-id="822fe-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-501">COLUMN_TYPE</span></span>|<span data-ttu-id="822fe-502">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-502">Int16</span></span>|  
|<span data-ttu-id="822fe-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-503">DATA_TYPE</span></span>|<span data-ttu-id="822fe-504">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-504">Int16</span></span>|  
|<span data-ttu-id="822fe-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-505">TYPE_NAME</span></span>|<span data-ttu-id="822fe-506">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-506">String</span></span>|  
|<span data-ttu-id="822fe-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="822fe-507">PRECISION</span></span>|<span data-ttu-id="822fe-508">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-508">Int32</span></span>|  
|<span data-ttu-id="822fe-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-509">LENGTH</span></span>|<span data-ttu-id="822fe-510">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-510">Int32</span></span>|  
|<span data-ttu-id="822fe-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="822fe-511">SCALE</span></span>|<span data-ttu-id="822fe-512">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-512">Int16</span></span>|  
|<span data-ttu-id="822fe-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="822fe-513">RADIX</span></span>|<span data-ttu-id="822fe-514">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-514">Int16</span></span>|  
|<span data-ttu-id="822fe-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-515">NULLABLE</span></span>|<span data-ttu-id="822fe-516">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-516">Int16</span></span>|  
|<span data-ttu-id="822fe-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-517">REMARKS</span></span>|<span data-ttu-id="822fe-518">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-518">String</span></span>|  
|<span data-ttu-id="822fe-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="822fe-519">OVERLOAD</span></span>|<span data-ttu-id="822fe-520">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-520">Int32</span></span>|  
|<span data-ttu-id="822fe-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="822fe-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="822fe-522">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="822fe-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="822fe-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="822fe-524">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="822fe-524">ColumnName</span></span>|<span data-ttu-id="822fe-525">DataType</span><span class="sxs-lookup"><span data-stu-id="822fe-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="822fe-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="822fe-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="822fe-527">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-527">String</span></span>|  
|<span data-ttu-id="822fe-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="822fe-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="822fe-529">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-529">String</span></span>|  
|<span data-ttu-id="822fe-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="822fe-531">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-531">String</span></span>|  
|<span data-ttu-id="822fe-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-532">COLUMN_NAME</span></span>|<span data-ttu-id="822fe-533">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-533">String</span></span>|  
|<span data-ttu-id="822fe-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-534">COLUMN_TYPE</span></span>|<span data-ttu-id="822fe-535">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-535">Int16</span></span>|  
|<span data-ttu-id="822fe-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-536">DATA_TYPE</span></span>|<span data-ttu-id="822fe-537">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-537">Int16</span></span>|  
|<span data-ttu-id="822fe-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="822fe-538">TYPE_NAME</span></span>|<span data-ttu-id="822fe-539">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-539">String</span></span>|  
|<span data-ttu-id="822fe-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="822fe-540">COLUMN_SIZE</span></span>|<span data-ttu-id="822fe-541">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-541">Int32</span></span>|  
|<span data-ttu-id="822fe-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="822fe-543">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-543">Int32</span></span>|  
|<span data-ttu-id="822fe-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="822fe-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="822fe-545">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-545">Int16</span></span>|  
|<span data-ttu-id="822fe-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="822fe-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="822fe-547">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-547">Int16</span></span>|  
|<span data-ttu-id="822fe-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-548">NULLABLE</span></span>|<span data-ttu-id="822fe-549">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-549">Int16</span></span>|  
|<span data-ttu-id="822fe-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="822fe-550">REMARKS</span></span>|<span data-ttu-id="822fe-551">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-551">String</span></span>|  
|<span data-ttu-id="822fe-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="822fe-552">COLUMN_DEF</span></span>|<span data-ttu-id="822fe-553">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-553">String</span></span>|  
|<span data-ttu-id="822fe-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="822fe-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="822fe-555">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-555">Int16</span></span>|  
|<span data-ttu-id="822fe-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="822fe-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="822fe-557">Int16</span><span class="sxs-lookup"><span data-stu-id="822fe-557">Int16</span></span>|  
|<span data-ttu-id="822fe-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="822fe-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="822fe-559">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-559">Int32</span></span>|  
|<span data-ttu-id="822fe-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="822fe-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="822fe-561">Int32</span><span class="sxs-lookup"><span data-stu-id="822fe-561">Int32</span></span>|  
|<span data-ttu-id="822fe-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="822fe-562">IS_NULLABLE</span></span>|<span data-ttu-id="822fe-563">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="822fe-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="822fe-564">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="822fe-564">See Also</span></span>  
 [<span data-ttu-id="822fe-565">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="822fe-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
