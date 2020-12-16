Used this in a situation where we needed to strip `\\n` characters from a string that was coming back from GraphCMS.

```
{this.props.text.split('\\n').map((item, index) => {
  return <Fragment key={index}>{item}<br/></Fragment>
})}
```