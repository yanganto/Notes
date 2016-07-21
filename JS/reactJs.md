# JSX
```
var GroupManagePanel = React.createClass({
 getInitialState: function() {
    var has_invitation = this.props.invitation == undefined ? false : true;
    var accept = this.props.accept == undefined ? false : true;
    return {has_invitation: has_invitation, accept: accept};
  },
  render: function() {
    return (
      <div style={{width: '800px', height: '650px', padding: '20px', backgroundColor: '#eaf0f4'}}>
          <p style={{position: 'absolute', bottom: '20px'}}>
              Some thing ... 
          </p>
        <br />
        { this.state.accept ?
          <button className="btn" style={{float: 'right'}} onClick={this.props.close}>
            Close
          </button>
          :
          <button className="btn" style={{float: 'right'}} onClick={this.props.save}>
            Save & Next step
          </button>
        }
      </div>
    );
  }
});
```

---
# Compile
`babel --plugins transform-react-jsx int.jsx > out.js`

---
# Render
 ```
var Factory = React.createFactory(CampaignDetailBox);
ReactDOM.render(
      Factory({
          some_id: e.target.dataset.cid,
          some_function: function(){ return 0}
      }),
      document.getElementById('campaign_detail_box')
);
```           
