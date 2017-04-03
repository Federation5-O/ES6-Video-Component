# ES6-Video-Component

// jshint esnext: true

class Greet extends React.Component
{
  render()
  {
    if (this.props.name === undefined)
    {
      return (
        <h3>Hello, BEASTRON CARPIO !!!! :P :P :P :P</h3>
      );      
    }
    else
    {
      return (
        <h3>Hello {this.props.name}, from React!</h3>
      );      
    }
  }
}

class Video extends React.Component
{
  render()
  {
    if (this.props.src.includes('youtube.com'))
    {
      return (
        <iframe src={this.props.src} frameborder="0" allowfullscreen>
        </iframe>
      );
    }
    else if(this.props.src.includes('youtu.be'))
    {
      const slug = this.props.src.slice(this.props.src.lastIndexOf('/'));
      const src = `https://www.youtube.com/embed/${slug}`;
      
      return (
        <Video src={src} />
      );
    }
    else
    {
      return (
        <video src={this.props.src} controls={true} />
      );      
    }
  }
}

class App extends React.Component
{
  render()
  {
    return (
      <div>
        <Greet />
        />
        <Video src="https://www.youtu.be/R51LMIAJtsc" />
        <Video src="https://www.youtu.be/TeWlsNiTMlE"/>
        
      </div>
    );
  }
}

ReactDOM.render(<App />, document.getElementById('app'));


