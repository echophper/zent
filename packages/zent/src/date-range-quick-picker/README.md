## DateRangeQuickPicker

简单的时间范围选择组件, 提供前7天和前30天的快速选择.

### 使用场景

列表页 filter 区域快速选择日期使用

### 代码演示

:::demo 基础用法
```js
import { DateRangeQuickPicker } from 'zent';

class Simple extends Component {
	state = {
	};

	handleChange = (value, chooseDays) => {
		console.log(value, chooseDays);
		this.setState({
			value,
			chooseDays
		});
	};

	handleChange1 = (value, chooseDays) => {
		console.log(value, chooseDays);
		this.setState({
			value1: value,
			chooseDays1: chooseDays
		});
	}

  render() {
    const { value, chooseDays, value1, chooseDays1 } = this.state;

    return (
			<div>
				<DateRangeQuickPicker
					onChange={this.handleChange}
					value={value}
					format="YYYY-MM-DD HH:mm:ss"
					chooseDays={chooseDays}
				/>
				<br />
				<DateRangeQuickPicker
					onChange={this.handleChange1}
					value={value1}
					format="YYYY-MM-DD"
					chooseDays={chooseDays1}
					preset={[{
						text: '最近7天',
						value: 7
					}, {
						text: '最近3个月',
						value: 90
					}, {
						text: '最近6个月',
						value: 180
					}]}
				/>
			</div>
    );
  }
}

ReactDOM.render(
	<Simple />
	, mountNode
);

```
:::


### API

| 参数            | 说明               | 类型             | 默认值      | 备选值     |
|------          |------              |------            |--------    |--------   |
| prefix         | 自定义前缀           | string          | `'zent'`    |           |
| className      | 自定义类名          | string            |   ''      |              |
| preset         | 自定义快捷选项      | array          | `[{text: '最近7天', value: 7}, {text: '最近30天', value: 30}]`    |           |
| onChange       | change time func  | func          |         |              |
| value          | 起始、结束时间       | array        |   `[]`        |             |
| format         | 返回日期字符串格式   |  string       |   `'YYYY-MM-DD'` 或 `'YYYY-MM-DD HH:mm:ss'`   |           |
| chooseDays     | 选择天数           |  number       |    `0`        |         |
