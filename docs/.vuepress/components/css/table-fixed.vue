<template>
  <div>
    <div class="normal-table">
      <div class="table-left-fixed">
        <table class="table">
          <thead>
            <tr class="table-thead">
              <th class="sort-th">表头1</th>
            </tr>
          </thead>
        </table>
        <div class="table-wrap table-wrap-fixed" name="table-fixed-scroll">
          <table class="table">
            <tbody class="table-tbody">
              <tr>
                <td>第1列</td>
              </tr>
              <tr>
                <td>第2列</td>
              </tr>
              <tr>
                <td>第3列</td>
              </tr>
              <tr>
                <td>第4列</td>
              </tr>
              <tr>
                <td>第5列</td>
              </tr>
              <tr>
                <td>第6列</td>
              </tr>
            </tbody>
          </table>
        </div>
        <table class="table table-total">
          <tbody>
            <tr class="table-tr">
              <td>总计</td>
            </tr>
          </tbody>
        </table>
      </div>
      <div class="table-content">
        <table class="table">
          <thead>
            <tr class="table-thead">
              <th class="sort-th">表头1</th>
              <th class="sort-th">表头2</th>
              <th class="sort-th">表头3</th>
              <th class="sort-th">表头4</th>
            </tr>
          </thead>
        </table>

        <div class="table-wrap" name="table-scroll">
          <table class="table">
            <tbody class="table-tbody">
              <tr>
                <td>值1</td>
                <td>值2</td>
                <td>值3</td>
                <td>值4</td>
              </tr>
              <tr>
                <td>值1</td>
                <td>值2</td>
                <td>值3</td>
                <td>值4</td>
              </tr>
              <tr>
                <td>值1</td>
                <td>值2</td>
                <td>值3</td>
                <td>值4</td>
              </tr>
              <tr>
                <td>值1</td>
                <td>值2</td>
                <td>值3</td>
                <td>值4</td>
              </tr>
              <tr>
                <td>值1</td>
                <td>值2</td>
                <td>值3</td>
                <td>值4</td>
              </tr>
              <tr>
                <td>值1</td>
                <td>值2</td>
                <td>值3</td>
                <td>值4</td>
              </tr>
            </tbody>
          </table>
        </div>
        <table class="table table-total">
          <tbody>
            <tr class="table-tr">
              <td>总计1</td>
              <td>总计2</td>
              <td>总计3</td>
              <td>总计4</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<style lang="stylus">
::-webkit-scrollbar-track-piece {
  background: #f1f1f1;
}

::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

::-webkit-scrollbar-thumb {
  background: #bababa;
  border-radius: 4px;
}

.normal-table {
  width: 250px;
  position: relative;
}

.table {
  margin: 0;
  display: table;
  -webkit-overflow-scrolling: touch;
}

.table {
  th, td {
    width: 80px;
    min-width: 80px;
    font-size: 13px;
    padding: 8px 10px;
    font-weight: normal;
  }
}

.table-thead {
  background: #ececec;
  color: #999;
  th:first-child {
    border-right: 1px solid #c9c9cc;
  }
}

.table-tr {
  td {
    text-align: right;
    td:first-child {
      border-right: 1px solid #c9c9cc;
      text-align: left;
    }
  }
}

.table {
  border: 0;
  border-spacing: 0;
}

.table-left-fixed {
  .table-thead {
    td {
      display: none;
    }
  }
}

.table-left-fixed {
  .table-thead {
    td:first-child {
      display: block;
    }
  }
}

.table-left-fixed {
  position: absolute;
  background: #fff;
  z-index: 1;
}

.table-content {
  position: relative;
  overflow: hidden;
  overflow-x: auto;
}

.table-wrap {
  display: inline-block;
  max-height: 124px;
  overflow: hidden;
  overflow-y: auto;
}

.table-wrap-fixed {
  overflow: hidden;
}

.table-tbody {
  td {
    text-align: right;
  }
}

.table-total {
  position: relative;
  top: -4px;
}
</style>

<script>
export default {
  mounted() {
    const tableScrollDoms = document.getElementsByName("table-scroll");
    tableScrollDoms.forEach(ele => {
      ele.removeEventListener("scroll", () => {});
      ele.addEventListener("scroll", function() {
        this.parentNode.previousElementSibling.children[1].scrollTop = this.scrollTop;
      });
    });

    const tableFixedScrollDoms = document.getElementsByName(
      "table-fixed-scroll"
    );
    tableFixedScrollDoms.forEach(ele => {
      ele.removeEventListener("scroll", () => {});
      ele.addEventListener("scroll", function() {
        this.parentNode.nextElementSibling.children[1].scrollTop = this.scrollTop;
      });
    });
  }
};
</script>
